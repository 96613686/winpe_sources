# Windows::Internal::CapabilityAccess::Private::IsFirstDeviceBoot(void)

- ea: `0x180043fe8`
- end: `0x1800441b1`
- name: `?IsFirstDeviceBoot@Private@CapabilityAccess@Internal@Windows@@YA_NXZ`
- size: `457`
- prototype: `bool __fastcall(Windows::Internal::CapabilityAccess::Private *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068310`

## callees

- `0x18002392c`
- `0x1800299c4`
- `0x18002f280`
- `0x18003ce34`
- `0x180041f2c`
- `0x180043fe8`
- `0x180058fb8`
- `0x18005ca18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004408e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800440ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180044164`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004408e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800440ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180044164`

## string_xrefs

- `0x180044080`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Internal::CapabilityAccess::Private::IsFirstDeviceBoot(
        Windows::Internal::CapabilityAccess::Private *this)
{
  Windows::Internal::CapabilityAccess::Private *v1; // rcx
  wil::details::in1diag3 *v2; // r10
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // r9d
  unsigned int v7; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-30h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-30h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-30h]
  DWORD dwOptionsc; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY phkResult; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  HKEY v15; // [rsp+70h] [rbp+20h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<unsigned long,4>::load(&Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState) )
    wil::details::in1diag3::Throw_Hr(
      v2,
      (void *)0x256,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      dwOptions);
  if ( !Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_isFirstBoot )
    return 0;
  if ( Windows::Internal::CapabilityAccess::Private::GetOobeState(v1) == 2 )
  {
    hKey = 0;
    phkResult = 0;
    v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
           0,
           0,
           0,
           0xF013Fu,
           0,
           &hKey,
           0);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x867,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v4,
        dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v5 = RegCreateKeyExW(hKey, L"Notifications", 0, 0, 0, 0xF013Fu, 0, &phkResult, 0);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x86A,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v5,
        dwOptionsb);
    Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(
      (Windows::Internal::CapabilityAccess::Private *)phkResult,
      (HKEY)&stru_1800D8400,
      (const unsigned __int16 *)1,
      v6);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v15,
      0);
    v7 = RegCreateKeyExW(phkResult, L"FirstBoot", 0, 0, 1u, 0xF013Fu, 0, &v15, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x870,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v7,
        dwOptionsc);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return 1;
}

```

## disassembly

```asm
0x180043fe8  mov     [rsp-8+arg_18], rbx
0x180043fed  push    rbp
0x180043fee  mov     rbp, rsp
0x180043ff1  sub     rsp, 50h
0x180043ff5  mov     r10, [rbp+8]
0x180043ff9  lea     rcx, ?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x180044000  call    ?load@?$_Atomic_storage@K$03@std@@QEBAKW4memory_order@2@@Z; std::_Atomic_storage<ulong,4>::load(std::memory_order)
0x180044005  cmp     eax, 1
0x180044008  jnb     short loc_180044025
0x18004400a  mov     r9d, 8000FFFFh; char *
0x180044010  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x180044017  mov     edx, 256h; void *
0x18004401c  mov     rcx, r10; this
0x18004401f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044025  xor     ebx, ebx
0x180044027  cmp     cs:?m_isFirstBoot@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@0_NA, bl; bool Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_isFirstBoot
0x18004402d  jnz     short loc_180044036
0x18004402f  xor     al, al
0x180044031  jmp     loc_1800441A6
0x180044036  call    ?GetOobeState@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::GetOobeState(void)
0x18004403b  cmp     eax, 2
0x18004403e  jnz     loc_1800441A4
0x180044044  mov     [rbp+hKey], rbx
0x180044048  mov     [rbp+arg_0], rbx
0x18004404c  mov     [rbp+arg_10], rbx
0x180044050  xor     edx, edx
0x180044052  lea     rcx, [rbp+hKey]
0x180044056  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004405b  mov     [rsp+50h+lpdwDisposition], rbx; lpdwDisposition
0x180044060  lea     rax, [rbp+hKey]
0x180044064  mov     [rsp+50h+phkResult], rax; phkResult
0x180044069  mov     [rsp+50h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18004406e  mov     [rsp+50h+samDesired], 0F013Fh; samDesired
0x180044076  mov     [rsp+50h+dwOptions], ebx; unsigned int
0x18004407a  xor     r9d, r9d; lpClass
0x18004407d  xor     r8d, r8d; Reserved
0x180044080  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180044087  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004408e  call    cs:__imp_RegCreateKeyExW
0x180044094  mov     rcx, [rbp+8]; this
0x180044098  test    eax, eax
0x18004409a  jz      short loc_1800440B1
0x18004409c  mov     r9d, eax; char *
0x18004409f  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800440a6  mov     edx, 867h; void *
0x1800440ab  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800440b1  xor     edx, edx
0x1800440b3  lea     rcx, [rbp+arg_0]
0x1800440b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800440bc  mov     [rsp+50h+lpdwDisposition], rbx; lpdwDisposition
0x1800440c1  lea     rax, [rbp+arg_0]
0x1800440c5  mov     [rsp+50h+phkResult], rax; phkResult
0x1800440ca  mov     [rsp+50h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800440cf  mov     [rsp+50h+samDesired], 0F013Fh; samDesired
0x1800440d7  mov     [rsp+50h+dwOptions], ebx; unsigned int
0x1800440db  xor     r9d, r9d; lpClass
0x1800440de  xor     r8d, r8d; Reserved
0x1800440e1  lea     rdx, aNotifications; "Notifications"
0x1800440e8  mov     rcx, [rbp+hKey]; hKey
0x1800440ec  call    cs:__imp_RegCreateKeyExW
0x1800440f2  mov     rcx, [rbp+8]; this
0x1800440f6  test    eax, eax
0x1800440f8  jz      short loc_18004410F
0x1800440fa  mov     r9d, eax; char *
0x1800440fd  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044104  mov     edx, 86Ah; void *
0x180044109  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004410f  mov     r8d, 1; unsigned __int16 *
0x180044115  lea     rdx, stru_1800D8400; HKEY
0x18004411c  mov     rcx, [rbp+arg_0]; this
0x180044120  call    ?RegSetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGI@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(HKEY__ *,ushort const *,uint)
0x180044125  xor     edx, edx
0x180044127  lea     rcx, [rbp+arg_10]
0x18004412b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180044130  mov     [rsp+50h+lpdwDisposition], rbx; lpdwDisposition
0x180044135  lea     rax, [rbp+arg_10]
0x180044139  mov     [rsp+50h+phkResult], rax; phkResult
0x18004413e  mov     [rsp+50h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180044143  mov     [rsp+50h+samDesired], 0F013Fh; samDesired
0x18004414b  mov     [rsp+50h+dwOptions], 1; unsigned int
0x180044153  xor     r9d, r9d; lpClass
0x180044156  xor     r8d, r8d; Reserved
0x180044159  lea     rdx, aFirstboot; "FirstBoot"
0x180044160  mov     rcx, [rbp+arg_0]; hKey
0x180044164  call    cs:__imp_RegCreateKeyExW
0x18004416a  mov     rcx, [rbp+8]; this
0x18004416e  test    eax, eax
0x180044170  jz      short loc_180044187
0x180044172  mov     r9d, eax; char *
0x180044175  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004417c  mov     edx, 870h; void *
0x180044181  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180044187  lea     rcx, [rbp+arg_10]
0x18004418b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044190  nop
0x180044191  lea     rcx, [rbp+arg_0]
0x180044195  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004419a  nop
0x18004419b  lea     rcx, [rbp+hKey]
0x18004419f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800441a4  mov     al, 1
0x1800441a6  mov     rbx, [rsp+50h+arg_18]
0x1800441ab  add     rsp, 50h
0x1800441af  pop     rbp
0x1800441b0  retn
```
