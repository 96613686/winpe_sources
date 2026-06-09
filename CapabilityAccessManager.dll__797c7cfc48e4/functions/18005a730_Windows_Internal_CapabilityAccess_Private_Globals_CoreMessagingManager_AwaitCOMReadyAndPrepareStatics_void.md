# Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::AwaitCOMReadyAndPrepareStatics(void)

- ea: `0x18005a730`
- end: `0x18005a8b7`
- name: `?AwaitCOMReadyAndPrepareStatics@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAXXZ`
- size: `391`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c000`

## callees

- `0x1800094c0`
- `0x180016d74`
- `0x180017bc4`
- `0x18001f5f4`
- `0x180021074`
- `0x180045f78`
- `0x18005a730`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005a758`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005a758`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a770`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a770`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005a7be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005a7be`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005a7e6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005a7e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a7a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005a7a5`

## string_xrefs

- `0x18005a79e`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::AwaitCOMReadyAndPrepareStatics(void)
{
  const char *v0; // r9
  const char *v1; // r9
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING, __int64 *); // rbx
  int v6; // eax
  int v7[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( WaitForSingleObject(
         Windows::Internal::CapabilityAccess::Private::Globals::ServiceStateTracker::m_comReadyEvent,
         0xFFFFFFFF) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3A9,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v0);
  }
  AcquireSRWLockShared(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_lock);
  *(_QWORD *)v7 = &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_lock;
  if ( !Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_initialized )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v1);
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
         0x3Cu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics);
  ActivationFactory = RoGetActivationFactory(
                        v2,
                        &GUID_42947746_4ea0_48c2_9274_062ed61f8daa,
                        &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3B4,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v7[0]);
  v4 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics
                                                             + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_graphicsCaptureProgrammaticUsage);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&string,
    c_szCapabilityGraphicsCaptureProgrammatic);
  v6 = v5(
         v4,
         string,
         &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_graphicsCaptureProgrammaticUsage);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3BB,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      (const char *)(unsigned int)v6,
      v7[0]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v7);
}

```

## disassembly

```asm
0x18005a730  mov     [rsp+arg_0], rbx
0x18005a735  push    rdi
0x18005a736  sub     rsp, 50h
0x18005a73a  mov     rax, cs:__security_cookie
0x18005a741  xor     rax, rsp
0x18005a744  mov     [rsp+58h+var_10], rax
0x18005a749  mov     rbx, [rsp+58h]
0x18005a74e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005a751  mov     rcx, cs:?m_comReadyEvent@ServiceStateTracker@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A; hHandle
0x18005a758  call    cs:__imp_WaitForSingleObject
0x18005a75e  test    eax, eax
0x18005a760  jnz     loc_18005A87B
0x18005a766  lea     rbx, ?m_lock@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_lock
0x18005a76d  mov     rcx, rbx; SRWLock
0x18005a770  call    cs:__imp_AcquireSRWLockShared
0x18005a776  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18005a77b  mov     al, cs:?m_initialized@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@_N@std@@A; std::atomic<bool> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_initialized
0x18005a781  nop
0x18005a782  mov     rcx, [rsp+58h]; this
0x18005a787  test    al, al
0x18005a789  jz      loc_18005A890
0x18005a78f  lea     r9, [rsp+58h+string]; string
0x18005a794  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18005a799  mov     edx, 3Ch ; '<'; length
0x18005a79e  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x18005a7a5  call    cs:__imp_WindowsCreateStringReference
0x18005a7ab  test    eax, eax
0x18005a7ad  jns     short loc_18005A7C4
0x18005a7af  xor     r9d, r9d; lpArguments
0x18005a7b2  xor     r8d, r8d; nNumberOfArguments
0x18005a7b5  lea     edx, [r9+1]; dwExceptionFlags
0x18005a7b9  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005a7be  call    cs:__imp_RaiseException
0x18005a7c4  mov     rbx, [rsp+58h+string]
0x18005a7c9  lea     rcx, ?m_usageStatics@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics
0x18005a7d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a7d5  lea     r8, ?m_usageStatics@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics
0x18005a7dc  lea     rdx, _GUID_42947746_4ea0_48c2_9274_062ed61f8daa
0x18005a7e3  mov     rcx, rbx
0x18005a7e6  call    cs:__imp_RoGetActivationFactory
0x18005a7ec  mov     rcx, [rsp+58h]; this
0x18005a7f1  test    eax, eax
0x18005a7f3  js      loc_18005A8A2
0x18005a7f9  mov     rdi, cs:?m_usageStatics@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_usageStatics
0x18005a800  mov     rax, [rdi]
0x18005a803  mov     rbx, [rax+30h]
0x18005a807  lea     rcx, ?m_graphicsCaptureProgrammaticUsage@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_graphicsCaptureProgrammaticUsage
0x18005a80e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a813  mov     rdx, cs:?c_szCapabilityGraphicsCaptureProgrammatic@@3QEBGEB; unsigned __int16 *
0x18005a81a  lea     rcx, [rsp+58h+string]; this
0x18005a81f  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18005a824  lea     r8, ?m_graphicsCaptureProgrammaticUsage@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_graphicsCaptureProgrammaticUsage
0x18005a82b  mov     rdx, [rsp+58h+string]
0x18005a830  mov     rcx, rdi
0x18005a833  mov     rax, rbx
0x18005a836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a83b  mov     rcx, [rsp+58h]; this
0x18005a840  test    eax, eax
0x18005a842  js      short loc_18005A866
0x18005a844  lea     rcx, [rsp+58h+var_38]
0x18005a849  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005a84e  mov     rcx, [rsp+58h+var_10]
0x18005a853  xor     rcx, rsp; StackCookie
0x18005a856  call    __security_check_cookie
0x18005a85b  mov     rbx, [rsp+58h+arg_0]
0x18005a860  add     rsp, 50h
0x18005a864  pop     rdi
0x18005a865  retn
0x18005a866  mov     r9d, eax; char *
0x18005a869  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a870  mov     edx, 3BBh; void *
0x18005a875  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005a87b  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a882  mov     edx, 3A9h; void *
0x18005a887  mov     rcx, rbx; this
0x18005a88a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005a890  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a897  mov     edx, 3B0h; void *
0x18005a89c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005a8a2  mov     r9d, eax; char *
0x18005a8a5  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a8ac  mov     edx, 3B4h; void *
0x18005a8b1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
