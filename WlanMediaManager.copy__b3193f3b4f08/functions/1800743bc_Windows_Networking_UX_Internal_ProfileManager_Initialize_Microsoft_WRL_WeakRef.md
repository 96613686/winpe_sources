# Windows::Networking::UX::Internal::ProfileManager::Initialize(Microsoft::WRL::WeakRef)

- ea: `0x1800743bc`
- end: `0x1800746af`
- name: `?Initialize@ProfileManager@Internal@UX@Networking@Windows@@QEAAJVWeakRef@WRL@Microsoft@@@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150e0`

## callees

- `0x180008e30`
- `0x18000bbf4`
- `0x18000de4c`
- `0x1800121e8`
- `0x1800141a0`
- `0x180015348`
- `0x18001ceb8`
- `0x18001d4d4`
- `0x1800289dc`
- `0x180028af8`
- `0x18005859c`
- `0x180073b40`
- `0x180073b7c`
- `0x180073cd8`
- `0x1800743bc`
- `0x18007a4e8`
- `0x18007d4bc`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1800744d2`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1800744d2`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180074638`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180074638`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18007446a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18007446a`
- `wlanapi!WlanWcmGetProfileList` at `0x180074543`
- `wlanapi!WlanWcmGetProfileList` at `0x180074543`
- `wlanapi!WlanRegisterNotification` at `0x1800744b5`
- `wlanapi!WlanRegisterNotification` at `0x1800744b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::Internal::ProfileManager::Initialize(void **a1, void **a2)
{
  PHANDLE CurrentEffectiveUserImpersonationToken; // rax
  DWORD v5; // eax
  DWORD v6; // ebx
  DWORD i; // esi
  const struct _GUID *p_InterfaceGuid; // r14
  signed int ProfileList; // ebx
  __int64 v10; // rdx
  void *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  const char *v16; // r9
  __int64 result; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  _BYTE v20[8]; // [rsp+40h] [rbp-58h] BYREF
  void **p_phNewToken; // [rsp+48h] [rbp-50h] BYREF
  struct WCM_WLAN_PROFILE_INFO_LIST *v22; // [rsp+50h] [rbp-48h] BYREF
  char v23; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  DWORD pdwNegotiatedVersion; // [rsp+A0h] [rbp+8h] BYREF
  void **v26; // [rsp+A8h] [rbp+10h]
  void *phNewToken; // [rsp+B0h] [rbp+18h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+B8h] [rbp+20h] BYREF

  v26 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids);
  wil::EnterCriticalSection(v20, a1 + 1);
  try
  {
    CurrentEffectiveUserImpersonationToken = Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(&phNewToken);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1 + 9,
      CurrentEffectiveUserImpersonationToken);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    pdwNegotiatedVersion = 2;
    ppInterfaceList = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(
      a1,
      -1);
    v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, a1);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 == 1220 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      v6 = WlanRegisterNotification(
             *a1,
             8u,
             1,
             Windows::Networking::UX::Internal::ProfileManager::WlanNotificationCallback,
             a1,
             0,
             0);
      if ( !v6 )
      {
        v6 = WlanEnumInterfaces(*a1, 0, &ppInterfaceList);
        if ( !v6 )
        {
          for ( i = 0; i < ppInterfaceList->dwNumberOfItems; ++i )
          {
            p_InterfaceGuid = &ppInterfaceList->InterfaceInfo[i].InterfaceGuid;
            if ( p_InterfaceGuid[33].Data1 )
            {
              phNewToken = 0;
              p_phNewToken = &phNewToken;
              v22 = 0;
              v23 = 1;
              ProfileList = WlanWcmGetProfileList(p_InterfaceGuid, 0, &v22);
              wil::details::out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>>::~out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>>(&p_phNewToken);
              if ( ProfileList )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  if ( ProfileList > 0 )
                    ProfileList = (unsigned __int16)ProfileList | 0x80070000;
                  WPP_SF__guid_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids,
                    p_InterfaceGuid,
                    ProfileList);
                }
                v6 = 0;
              }
              else
              {
                v6 = 0;
                Windows::Networking::UX::Internal::ProfileManager::CacheProfileList(
                  a1,
                  v10,
                  p_InterfaceGuid,
                  (unsigned int *)phNewToken);
              }
              std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>(&phNewToken);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids);
            }
          }
          v11 = *a2;
          if ( a1[8] != *a2 )
          {
            phNewToken = *a2;
            Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&phNewToken);
            phNewToken = a1[8];
            a1[8] = v11;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &phNewToken,
              v12,
              v13);
          }
        }
      }
    }
    if ( ppInterfaceList )
      WlanFreeMemory(ppInterfaceList);
    if ( (int)v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids, v6);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2, v14, v15);
    result = v6;
  }
  catch ( ... )
  {
    pdwNegotiatedVersion = wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x56,
                             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\profilemanager\\lib\\profilemanager.cpp",
                             v16);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26, v18, v19);
    return pdwNegotiatedVersion;
  }
  return result;
}

```

## disassembly

```asm
0x1800743bc  mov     [rsp+arg_8], rdx
0x1800743c1  push    rbx
0x1800743c2  push    rsi
0x1800743c3  push    rdi
0x1800743c4  push    r13
0x1800743c6  push    r14
0x1800743c8  push    r15
0x1800743ca  sub     rsp, 68h
0x1800743ce  mov     r15, rdx
0x1800743d1  mov     rdi, rcx
0x1800743d4  lea     r13, WPP_GLOBAL_Control
0x1800743db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743e2  cmp     rcx, r13
0x1800743e5  jz      short loc_180074402
0x1800743e7  test    byte ptr [rcx+1Ch], 40h
0x1800743eb  jz      short loc_180074402
0x1800743ed  mov     edx, 0Ah
0x1800743f2  lea     r8, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids
0x1800743f9  mov     rcx, [rcx+10h]
0x1800743fd  call    WPP_SF_
0x180074402  lea     rdx, [rdi+8]
0x180074406  lea     rcx, [rsp+98h+var_58]
0x18007440b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180074410  nop
0x180074411  lea     rcx, [rsp+98h+phNewToken]; phNewToken
0x180074419  call    ?GetCurrentEffectiveUserImpersonationToken@Internal@UX@Networking@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::GetCurrentEffectiveUserImpersonationToken(void)
0x18007441e  lea     rcx, [rdi+48h]
0x180074422  mov     rdx, rax
0x180074425  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18007442a  lea     rcx, [rsp+98h+phNewToken]
0x180074432  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180074437  mov     ebx, 2
0x18007443c  mov     [rsp+98h+pdwNegotiatedVersion], ebx
0x180074443  mov     [rsp+98h+ppInterfaceList], 0
0x18007444f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180074453  mov     rcx, rdi
0x180074456  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18007445b  mov     r9, rdi; phClientHandle
0x18007445e  lea     r8, [rsp+98h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180074466  xor     edx, edx; pReserved
0x180074468  mov     ecx, ebx; dwClientVersion
0x18007446a  call    cs:__imp_WlanOpenHandle
0x180074470  mov     ebx, eax
0x180074472  test    eax, eax
0x180074474  jz      short loc_18007448B
0x180074476  cmp     eax, 4C4h
0x18007447b  jnz     loc_180074628
0x180074481  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180074486  jmp     loc_180074628
0x18007448b  mov     [rsp+98h+pdwPrevNotifSource], 0; pdwPrevNotifSource
0x180074494  mov     [rsp+98h+pReserved], 0; pReserved
0x18007449d  mov     [rsp+98h+pCallbackContext], rdi; pCallbackContext
0x1800744a2  lea     r9, ?WlanNotificationCallback@ProfileManager@Internal@UX@Networking@Windows@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x1800744a9  mov     edx, 8; dwNotifSource
0x1800744ae  lea     r8d, [rdx-7]; bIgnoreDuplicate
0x1800744b2  mov     rcx, [rdi]; hClientHandle
0x1800744b5  call    cs:__imp_WlanRegisterNotification
0x1800744bb  mov     ebx, eax
0x1800744bd  test    eax, eax
0x1800744bf  jnz     loc_180074628
0x1800744c5  lea     r8, [rsp+98h+ppInterfaceList]; ppInterfaceList
0x1800744cd  xor     edx, edx; pReserved
0x1800744cf  mov     rcx, [rdi]; hClientHandle
0x1800744d2  call    cs:__imp_WlanEnumInterfaces
0x1800744d8  mov     ebx, eax
0x1800744da  test    eax, eax
0x1800744dc  jnz     loc_180074628
0x1800744e2  xor     esi, esi
0x1800744e4  mov     rdx, [rsp+98h+ppInterfaceList]
0x1800744ec  cmp     esi, [rdx]
0x1800744ee  jnb     loc_1800745ED
0x1800744f4  mov     eax, esi
0x1800744f6  imul    r14, rax, 214h
0x1800744fd  add     r14, 8
0x180074501  add     r14, rdx
0x180074504  cmp     dword ptr [r14+210h], 0
0x18007450c  jz      loc_1800745BC
0x180074512  mov     [rsp+98h+phNewToken], 0
0x18007451e  lea     rax, [rsp+98h+phNewToken]
0x180074526  mov     [rsp+98h+var_50], rax
0x18007452b  mov     [rsp+98h+var_48], 0
0x180074534  mov     [rsp+98h+var_40], 1
0x180074539  lea     r8, [rsp+98h+var_48]
0x18007453e  xor     edx, edx
0x180074540  mov     rcx, r14
0x180074543  call    cs:__imp_?WlanWcmGetProfileList@@YAKPEBU_GUID@@PEAXPEAPEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z; WlanWcmGetProfileList(_GUID const *,void *,WCM_WLAN_PROFILE_INFO_LIST * *)
0x180074549  mov     ebx, eax
0x18007454b  lea     rcx, [rsp+98h+var_50]
0x180074550  call    ??1?$out_param_t@V?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@Internal@UX@Networking@Windows@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>>::~out_param_t<std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>>(void)
0x180074555  test    ebx, ebx
0x180074557  jz      short loc_1800745A5
0x180074559  mov     rcx, cs:WPP_GLOBAL_Control
0x180074560  cmp     rcx, r13
0x180074563  jz      short loc_180074594
0x180074565  test    byte ptr [rcx+1Ch], 2
0x180074569  jz      short loc_180074594
0x18007456b  test    ebx, ebx
0x18007456d  jle     short loc_180074578
0x18007456f  movzx   ebx, bx
0x180074572  or      ebx, 80070000h
0x180074578  mov     edx, 0Bh
0x18007457d  mov     dword ptr [rsp+98h+pCallbackContext], ebx
0x180074581  mov     r9, r14
0x180074584  lea     r8, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids
0x18007458b  mov     rcx, [rcx+10h]
0x18007458f  call    WPP_SF__guid_d
0x180074594  xor     ebx, ebx
0x180074596  lea     rcx, [rsp+98h+phNewToken]
0x18007459e  call    ??1?$unique_ptr@UWCM_WLAN_PROFILE_INFO_LIST@@VWlanWcmProfileListFreeMemoryHelper@Internal@UX@Networking@Windows@@@std@@QEAA@XZ; std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,Windows::Networking::UX::Internal::WlanWcmProfileListFreeMemoryHelper>(void)
0x1800745a3  jmp     short loc_1800745E6
0x1800745a5  xor     ebx, ebx
0x1800745a7  mov     r9, [rsp+98h+phNewToken]
0x1800745af  mov     r8, r14
0x1800745b2  mov     rcx, rdi
0x1800745b5  call    ?CacheProfileList@ProfileManager@Internal@UX@Networking@Windows@@AEAAXUwrite_lock_required@wil@@PEBU_GUID@@PEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z; Windows::Networking::UX::Internal::ProfileManager::CacheProfileList(wil::write_lock_required,_GUID const *,WCM_WLAN_PROFILE_INFO_LIST *)
0x1800745ba  jmp     short loc_180074596
0x1800745bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800745c3  cmp     rcx, r13
0x1800745c6  jz      short loc_1800745E6
0x1800745c8  test    byte ptr [rcx+1Ch], 8
0x1800745cc  jz      short loc_1800745E6
0x1800745ce  mov     edx, 0Ch
0x1800745d3  mov     r9, r14
0x1800745d6  lea     r8, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids
0x1800745dd  mov     rcx, [rcx+10h]
0x1800745e1  call    WPP_SF__guid_
0x1800745e6  inc     esi
0x1800745e8  jmp     loc_1800744E4
0x1800745ed  mov     rsi, [r15]
0x1800745f0  cmp     [rdi+40h], rsi
0x1800745f4  jz      short loc_180074628
0x1800745f6  mov     [rsp+98h+phNewToken], rsi
0x1800745fe  lea     rcx, [rsp+98h+phNewToken]
0x180074606  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18007460b  mov     rax, [rdi+40h]
0x18007460f  mov     [rsp+98h+phNewToken], rax
0x180074617  mov     [rdi+40h], rsi
0x18007461b  lea     rcx, [rsp+98h+phNewToken]
0x180074623  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074628  mov     rdx, [rsp+98h+ppInterfaceList]
0x180074630  test    rdx, rdx
0x180074633  jz      short loc_18007463E
0x180074635  mov     rcx, rdx; pMemory
0x180074638  call    cs:__imp_WlanFreeMemory
0x18007463e  test    ebx, ebx
0x180074640  jle     short loc_18007464B
0x180074642  movzx   ebx, bx
0x180074645  or      ebx, 80070000h
0x18007464b  mov     rcx, cs:WPP_GLOBAL_Control
0x180074652  cmp     rcx, r13
0x180074655  jz      short loc_180074676
0x180074657  test    byte ptr [rcx+1Ch], 40h
0x18007465b  jz      short loc_180074676
0x18007465d  mov     edx, 0Dh
0x180074662  mov     r9d, ebx
0x180074665  lea     r8, WPP_78c28dd014bb31f5e311c4a0d7ed64e7_Traceguids
0x18007466c  mov     rcx, [rcx+10h]
0x180074670  call    WPP_SF_d
0x180074675  nop
0x180074676  lea     rcx, [rsp+98h+var_58]
0x18007467b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180074680  nop
0x180074681  mov     rcx, r15
0x180074684  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180074689  mov     eax, ebx
0x18007468b  jmp     short loc_1800746A1
0x18007468d  mov     rcx, [rsp+98h+arg_8]
0x180074695  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007469a  mov     eax, [rsp+98h+pdwNegotiatedVersion]
0x1800746a1  add     rsp, 68h
0x1800746a5  pop     r15
0x1800746a7  pop     r14
0x1800746a9  pop     r13
0x1800746ab  pop     rdi
0x1800746ac  pop     rsi
0x1800746ad  pop     rbx
0x1800746ae  retn
```
