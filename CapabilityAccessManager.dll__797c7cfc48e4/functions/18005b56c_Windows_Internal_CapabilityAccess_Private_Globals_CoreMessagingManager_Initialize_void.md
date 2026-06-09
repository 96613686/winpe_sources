# Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::Initialize(void)

- ea: `0x18005b56c`
- end: `0x18005b71c`
- name: `?Initialize@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAJXZ`
- size: `432`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020310`

## callees

- `0x180016d54`
- `0x180017bc4`
- `0x180025b6c`
- `0x18002f280`
- `0x18003970c`
- `0x18003ce34`
- `0x180058dfc`
- `0x1800591c4`
- `0x18005b56c`
- `0x18005c8b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18005b68b`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18005b68b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005b63a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005b63a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b6cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b6cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b5d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b5d9`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18005b579`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18005b579`

## string_xrefs

- `0x18005b5cb`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::Initialize(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  unsigned int Uint32Value; // eax
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // r8
  __int64 v8; // rax
  int v9; // edx
  int v10; // ecx
  const char *v11; // r9
  bool *dwOptions; // [rsp+20h] [rbp-40h]
  _BYTE v13[16]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  RTL_SRWLOCK *v15; // [rsp+70h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+18h] BYREF

  if ( !(unsigned int)RtlGetCurrentServiceSessionId() )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v0 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
           0,
           0,
           0,
           0x20119u,
           0,
           &phkResult,
           0);
    if ( v0 )
    {
      v1 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x31F,
             (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
             (const char *)v0,
             (unsigned int)dwOptions);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return v1;
    }
    LOBYTE(v15) = 0;
    Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                    (Windows::Internal::CapabilityAccess::Private *)phkResult,
                    (HKEY)&stru_1800D7FE8,
                    L"InitializeUsageCoreMessaging",
                    (const unsigned __int16 *)&v15,
                    dwOptions);
    if ( (_BYTE)v15 && Uint32Value )
    {
      AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_lock);
      v15 = &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_lock;
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingThreadReadyEvent);
      if ( Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_initialized )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
        v1 = 0;
        goto LABEL_8;
      }
      v4 = (_QWORD *)std::thread::thread__lambda_63b5d6cab1e361052fd8439cbedfd6a8__0_(v13);
      v7 = v4;
      if ( *(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread
           + 2) )
      {
        _o_terminate(v6, v5, v4);
        __debugbreak();
      }
      v8 = *v4;
      v9 = *((_DWORD *)v7 + 2);
      v10 = *((_DWORD *)v7 + 3);
      *(_OWORD *)v7 = 0;
      Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread = v8;
      *(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread + 2) = v9;
      *(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread + 3) = v10;
      std::thread::~thread((std::thread *)v13);
      if ( WaitForSingleObject(
             Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingThreadReadyEvent,
             0xFFFFFFFF) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x379,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
          v11);
      }
      Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_initialized = 1;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x18005b56c  mov     [rsp-8+arg_10], rbx
0x18005b571  push    rbp
0x18005b572  mov     rbp, rsp
0x18005b575  sub     rsp, 60h
0x18005b579  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18005b57f  test    eax, eax
0x18005b581  jnz     loc_18005B6F7
0x18005b587  mov     [rbp+arg_8], 0
0x18005b58f  xor     edx, edx
0x18005b591  lea     rcx, [rbp+arg_8]
0x18005b595  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005b59a  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18005b5a3  lea     rax, [rbp+arg_8]
0x18005b5a7  mov     [rsp+60h+phkResult], rax; phkResult
0x18005b5ac  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005b5b5  mov     [rsp+60h+samDesired], 20119h; samDesired
0x18005b5bd  mov     dword ptr [rsp+60h+dwOptions], 0; bool *
0x18005b5c5  xor     r9d, r9d; lpClass
0x18005b5c8  xor     r8d, r8d; Reserved
0x18005b5cb  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b5d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b5d9  call    cs:__imp_RegCreateKeyExW
0x18005b5df  test    eax, eax
0x18005b5e1  jz      short loc_18005B5FF
0x18005b5e3  mov     rcx, [rbp+8]; this
0x18005b5e7  mov     r9d, eax; char *
0x18005b5ea  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005b5f1  mov     edx, 31Fh; void *
0x18005b5f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b5fb  mov     ebx, eax
0x18005b5fd  jmp     short loc_18005B666
0x18005b5ff  mov     byte ptr [rbp+arg_0], 0
0x18005b603  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x18005b607  lea     r8, aInitializeusag; "InitializeUsageCoreMessaging"
0x18005b60e  lea     rdx, stru_1800D7FE8; HKEY
0x18005b615  mov     rcx, [rbp+arg_8]; this
0x18005b619  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18005b61e  cmp     byte ptr [rbp+arg_0], 0
0x18005b622  jz      loc_18005B6EE
0x18005b628  test    eax, eax
0x18005b62a  jz      loc_18005B6EE
0x18005b630  lea     rbx, ?m_lock@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_lock
0x18005b637  mov     rcx, rbx; SRWLock
0x18005b63a  call    cs:__imp_AcquireSRWLockExclusive
0x18005b640  mov     [rbp+arg_0], rbx
0x18005b644  lea     rcx, ?m_coreMessagingThreadReadyEvent@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18005b64b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005b650  mov     al, cs:?m_initialized@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@_N@std@@A; std::atomic<bool> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_initialized
0x18005b656  nop
0x18005b657  test    al, al
0x18005b659  jz      short loc_18005B676
0x18005b65b  lea     rcx, [rbp+arg_0]
0x18005b65f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005b664  xor     ebx, ebx
0x18005b666  lea     rcx, [rbp+arg_8]
0x18005b66a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005b66f  mov     eax, ebx
0x18005b671  jmp     loc_18005B6F9
0x18005b676  lea     rcx, [rbp+var_10]
0x18005b67a  call    std__thread__thread__lambda_63b5d6cab1e361052fd8439cbedfd6a8__0_
0x18005b67f  mov     r8, rax
0x18005b682  cmp     dword ptr cs:?m_coreMessagingClientThread@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vthread@std@@A+8, 0; std::thread Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread
0x18005b689  jz      short loc_18005B692
0x18005b68b  call    cs:__imp__o_terminate
0x18005b691  int     3; Trap to Debugger
0x18005b692  xorps   xmm0, xmm0
0x18005b695  mov     rax, [rax]
0x18005b698  mov     edx, [r8+8]
0x18005b69c  mov     ecx, [r8+0Ch]
0x18005b6a0  movdqu  xmmword ptr [r8], xmm0
0x18005b6a5  mov     qword ptr cs:?m_coreMessagingClientThread@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vthread@std@@A, rax; std::thread Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread
0x18005b6ac  mov     dword ptr cs:?m_coreMessagingClientThread@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vthread@std@@A+8, edx; std::thread Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread
0x18005b6b2  mov     dword ptr cs:?m_coreMessagingClientThread@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vthread@std@@A+0Ch, ecx; std::thread Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingClientThread
0x18005b6b8  lea     rcx, [rbp+var_10]; this
0x18005b6bc  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18005b6c1  mov     rbx, [rbp+8]
0x18005b6c5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005b6c8  mov     rcx, cs:?m_coreMessagingThreadReadyEvent@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A; hHandle
0x18005b6cf  call    cs:__imp_WaitForSingleObject
0x18005b6d5  test    eax, eax
0x18005b6d7  jnz     short loc_18005B707
0x18005b6d9  mov     eax, 1
0x18005b6de  xchg    al, cs:?m_initialized@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@_N@std@@A; std::atomic<bool> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_initialized
0x18005b6e4  lea     rcx, [rbp+arg_0]
0x18005b6e8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005b6ed  nop
0x18005b6ee  lea     rcx, [rbp+arg_8]
0x18005b6f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005b6f7  xor     eax, eax
0x18005b6f9  mov     rbx, [rsp+60h+arg_10]
0x18005b701  add     rsp, 60h
0x18005b705  pop     rbp
0x18005b706  retn
0x18005b707  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005b70e  mov     edx, 379h; void *
0x18005b713  mov     rcx, rbx; this
0x18005b716  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
