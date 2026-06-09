# Windows::FileSystem::ReFs::ReFsDedupService::ServiceStart(void)

- ea: `0x14003536c`
- end: `0x140035609`
- name: `?ServiceStart@ReFsDedupService@ReFs@FileSystem@Windows@@QEAAXXZ`
- size: `669`
- prototype: `void __fastcall(Windows::FileSystem::ReFs::ReFsDedupService *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140031fbc`

## callees

- `0x140004870`
- `0x140015bc4`
- `0x140018710`
- `0x140018f7c`
- `0x1400196b8`
- `0x14003326c`
- `0x14003328c`
- `0x140033334`
- `0x1400341ac`
- `0x140034dd0`
- `0x140034f94`
- `0x14003536c`
- `0x140035884`
- `0x140035f08`
- `0x140035fa4`
- `0x1400377cc`
- `0x1400616b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400355ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400355ad`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140035496`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140035496`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003553d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003553d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140035425`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140035425`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1400354db`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1400354db`

## string_xrefs

- `0x1400353a2`: `ServiceStart`
- `0x1400355d0`: `onecore\base\fs\refsdedupsvc\exe\refsdedupservice.cpp`
- `0x1400355f7`: `onecore\base\fs\refsdedupsvc\exe\refsdedupservice.cpp`

## pseudocode

```c
void __fastcall Windows::FileSystem::ReFs::ReFsDedupService::ServiceStart(
        Windows::FileSystem::ReFs::ReFsDedupService *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  const char *v4; // r9
  HRESULT v5; // eax
  bool v6; // al
  DWORD LastError; // eax
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  const char *dwImpLevel; // [rsp+28h] [rbp-D8h]
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+54h] [rbp-ACh] BYREF
  PSECURITY_DESCRIPTOR pSecDesc; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v13[42]; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  pvData = 0;
  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v13);
  v13[0] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart::`vftable';
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart::StartActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart *)v13);
  if ( (Microsoft_Windows_ReFsDedupSvcEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, SvcStarted, v3, 1, SecurityDescriptor);
  pvData = 1;
  SecurityDescriptorSize = 0;
  SecurityDescriptor[0] = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0xB;;;AU)S:(ML;;NX;;;ME)",
          1u,
          SecurityDescriptor,
          &SecurityDescriptorSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\SvcLib\\inc\\SvcUtils.h",
      v4);
  Microsoft::Win32::Service::MakeAbsolute(&pSecDesc, SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(SecurityDescriptor);
  v5 = CoInitializeSecurity(pSecDesc, -1, 0, 0, 0, 2u, 0, 0x3000u, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\refsdedupservice.cpp",
      (const char *)(unsigned int)v5,
      dwAuthnLevel);
  Windows::FileSystem::ReFs::details__::ActivationFactoryRegistrar<std::tuple<winrt::Windows::Private::Storage::factory_implementation::DedupVolume,winrt::Windows::Private::Storage::factory_implementation::DedupSettings,winrt::Windows::Private::Storage::factory_implementation::VolumeSchedule>>::Register((char *)this + 72);
  Windows::FileSystem::ReFs::details__::ClassicComFactoryRegistrar<std::tuple<Windows::FileSystem::ReFs::DedupTaskHandlerFactory,Windows::FileSystem::ReFs::DedupScrubTaskHandlerFactory,Windows::FileSystem::ReFs::WnfWakeHandlerFactory>>::Register((char *)this + 80);
  SecurityDescriptorSize = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &SecurityDescriptorSize, 4) )
  {
    LastError = GetLastError();
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\refsdedupservice.cpp",
      (const char *)LastError,
      (unsigned int)"Failed to set image mitigation policy options",
      dwImpLevel);
  }
  Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::StartAsync((Windows::FileSystem::ReFs::ReFsDedupService *)((char *)this + 104));
  pvData = 0;
  SecurityDescriptorSize = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\FileSystem",
         L"ReFSDisableDedupTrim",
         0x10u,
         0,
         &pvData,
         &SecurityDescriptorSize) )
  {
    v6 = 0;
  }
  else
  {
    v6 = pvData != 0;
  }
  *((_BYTE *)this + 600) = v6;
  Windows::FileSystem::ReFs::ReFsDedupService::StartVolumeEnumeration(this);
  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v13,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_DESCRIPTOR *,void (*)(_SECURITY_DESCRIPTOR *),&void Microsoft::Win32::Service::private_details::FreeSecurityDescriptor(_SECURITY_DESCRIPTOR *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_DESCRIPTOR *,void (*)(_SECURITY_DESCRIPTOR *),&void Microsoft::Win32::Service::private_details::FreeSecurityDescriptor(_SECURITY_DESCRIPTOR *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR *,0,std::nullptr_t>>(&pSecDesc);
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart::~ServiceStart((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart *)v13);
}

```

## disassembly

```asm
0x14003536c  mov     [rsp-8+arg_8], rbx
0x140035371  mov     [rsp-8+arg_10], rdi
0x140035376  push    rbp
0x140035377  lea     rbp, [rsp-0D0h]
0x14003537f  sub     rsp, 1D0h
0x140035386  mov     rax, cs:__security_cookie
0x14003538d  xor     rax, rsp
0x140035390  mov     [rbp+0D0h+var_10], rax
0x140035397  mov     rdi, rcx
0x14003539a  mov     [rsp+1D0h+pvData], 0
0x1400353a2  lea     rdx, aServicestart; "ServiceStart"
0x1400353a9  lea     rcx, [rsp+1D0h+var_170]; struct wil::details::IFailureCallback *
0x1400353ae  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400353b3  lea     rax, ??_7ServiceStart@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart::`vftable'
0x1400353ba  mov     [rsp+1D0h+var_170], rax
0x1400353bf  lea     rcx, [rsp+1D0h+var_170]; this
0x1400353c4  call    ?StartActivity@ServiceStart@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart::StartActivity(void)
0x1400353c9  nop
0x1400353ca  test    cs:Microsoft_Windows_ReFsDedupSvcEnableBits, 1
0x1400353d1  jz      short loc_1400353F2
0x1400353d3  lea     rax, [rbp+0D0h+SecurityDescriptor]
0x1400353da  mov     qword ptr [rsp+1D0h+dwAuthnLevel], rax
0x1400353df  mov     r9d, 1
0x1400353e5  lea     rdx, SvcStarted
0x1400353ec  call    McGenEventWrite_EventWriteTransfer
0x1400353f1  nop
0x1400353f2  mov     [rsp+1D0h+pvData], 1
0x1400353fa  mov     [rsp+1D0h+SecurityDescriptorSize], 0
0x140035402  mov     [rbp+0D0h+SecurityDescriptor], 0
0x14003540d  lea     r9, [rsp+1D0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x140035412  lea     r8, [rbp+0D0h+SecurityDescriptor]; SecurityDescriptor
0x140035419  mov     edx, 1; StringSDRevision
0x14003541e  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0xB;;;AU)S:(ML;;NX;;;ME)"
0x140035425  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14003542c  nop     dword ptr [rax+rax+00h]
0x140035431  mov     rcx, [rbp+0D8h]; this
0x140035438  test    eax, eax
0x14003543a  jz      loc_1400355E2
0x140035440  lea     rdx, [rbp+0D0h+SecurityDescriptor]
0x140035447  lea     rcx, [rsp+1D0h+pSecDesc]
0x14003544c  call    ?MakeAbsolute@Service@Win32@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_DESCRIPTOR@@P6AXPEAU1@@Z$1?FreeSecurityDescriptor@private_details@Service@Win32@Microsoft@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@@Z; Microsoft::Win32::Service::MakeAbsolute(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x140035451  nop
0x140035452  lea     rcx, [rbp+0D0h+SecurityDescriptor]
0x140035459  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14003545e  mov     [rsp+1D0h+pReserved3], 0; pReserved3
0x140035467  mov     [rsp+1D0h+dwCapabilities], 3000h; dwCapabilities
0x14003546f  mov     [rsp+1D0h+pAuthList], 0; pAuthList
0x140035478  mov     [rsp+1D0h+dwImpLevel], 2; char *
0x140035480  mov     [rsp+1D0h+dwAuthnLevel], 0; int
0x140035488  xor     r9d, r9d; pReserved1
0x14003548b  xor     r8d, r8d; asAuthSvc
0x14003548e  or      edx, 0FFFFFFFFh; cAuthSvc
0x140035491  mov     rcx, [rsp+1D0h+pSecDesc]; pSecDesc
0x140035496  call    cs:__imp_CoInitializeSecurity
0x14003549d  nop     dword ptr [rax+rax+00h]
0x1400354a2  mov     rcx, [rbp+0D8h]; this
0x1400354a9  test    eax, eax
0x1400354ab  js      loc_1400355F4
0x1400354b1  lea     rcx, [rdi+48h]
0x1400354b5  call    ?Register@?$ActivationFactoryRegistrar@V?$tuple@UDedupVolume@factory_implementation@Storage@Private@Windows@winrt@@UDedupSettings@23456@UVolumeSchedule@23456@@std@@@details__@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::details__::ActivationFactoryRegistrar<std::tuple<winrt::Windows::Private::Storage::factory_implementation::DedupVolume,winrt::Windows::Private::Storage::factory_implementation::DedupSettings,winrt::Windows::Private::Storage::factory_implementation::VolumeSchedule>>::Register(void)
0x1400354ba  lea     rcx, [rdi+50h]
0x1400354be  call    ?Register@?$ClassicComFactoryRegistrar@V?$tuple@UDedupTaskHandlerFactory@ReFs@FileSystem@Windows@@UDedupScrubTaskHandlerFactory@234@UWnfWakeHandlerFactory@234@@std@@@details__@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::details__::ClassicComFactoryRegistrar<std::tuple<Windows::FileSystem::ReFs::DedupTaskHandlerFactory,Windows::FileSystem::ReFs::DedupScrubTaskHandlerFactory,Windows::FileSystem::ReFs::WnfWakeHandlerFactory>>::Register(void)
0x1400354c3  mov     [rsp+1D0h+SecurityDescriptorSize], 1
0x1400354cb  mov     ebx, 4
0x1400354d0  mov     r8d, ebx
0x1400354d3  lea     rdx, [rsp+1D0h+SecurityDescriptorSize]
0x1400354d8  lea     ecx, [rbx+0Ch]
0x1400354db  call    cs:__imp_SetProcessMitigationPolicy
0x1400354e2  nop     dword ptr [rax+rax+00h]
0x1400354e7  test    eax, eax
0x1400354e9  jz      loc_1400355AD
0x1400354ef  lea     rcx, [rdi+68h]
0x1400354f3  mov     rdx, rdi
0x1400354f6  call    ?StartAsync@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAAXPEAVReFsDedupService@234@@Z; Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::StartAsync(Windows::FileSystem::ReFs::ReFsDedupService *)
0x1400354fb  mov     [rsp+1D0h+pvData], 0
0x140035503  mov     [rsp+1D0h+SecurityDescriptorSize], ebx
0x140035507  lea     rax, [rsp+1D0h+SecurityDescriptorSize]
0x14003550c  mov     [rsp+1D0h+pAuthList], rax; pcbData
0x140035511  lea     rax, [rsp+1D0h+pvData]
0x140035516  mov     qword ptr [rsp+1D0h+dwImpLevel], rax; pvData
0x14003551b  mov     qword ptr [rsp+1D0h+dwAuthnLevel], 0; pdwType
0x140035524  lea     r9d, [rbx+0Ch]; dwFlags
0x140035528  lea     r8, aRefsdisableded; "ReFSDisableDedupTrim"
0x14003552f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fil"...
0x140035536  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14003553d  call    cs:__imp_RegGetValueW
0x140035544  nop     dword ptr [rax+rax+00h]
0x140035549  test    eax, eax
0x14003554b  jnz     short loc_140035556
0x14003554d  cmp     [rsp+1D0h+pvData], eax
0x140035551  setnz   al
0x140035554  jmp     short loc_140035558
0x140035556  xor     al, al
0x140035558  mov     [rdi+258h], al
0x14003555e  mov     rcx, rdi; Context
0x140035561  call    ?StartVolumeEnumeration@ReFsDedupService@ReFs@FileSystem@Windows@@AEAAXXZ; Windows::FileSystem::ReFs::ReFsDedupService::StartVolumeEnumeration(void)
0x140035566  xor     edx, edx
0x140035568  lea     rcx, [rsp+1D0h+var_170]
0x14003556d  call    ?Stop@?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140035572  nop
0x140035573  lea     rcx, [rsp+1D0h+pSecDesc]
0x140035578  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_DESCRIPTOR@@P6AXPEAU1@@Z$1?FreeSecurityDescriptor@private_details@Service@Win32@Microsoft@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_DESCRIPTOR *,void (*)(_SECURITY_DESCRIPTOR *),&Microsoft::Win32::Service::private_details::FreeSecurityDescriptor(_SECURITY_DESCRIPTOR *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_DESCRIPTOR *,void (*)(_SECURITY_DESCRIPTOR *),&Microsoft::Win32::Service::private_details::FreeSecurityDescriptor(_SECURITY_DESCRIPTOR *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x14003557d  nop
0x14003557e  lea     rcx, [rsp+1D0h+var_170]; this
0x140035583  call    ??1ServiceStart@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceStart::~ServiceStart(void)
0x140035588  mov     rcx, [rbp+0D0h+var_10]
0x14003558f  xor     rcx, rsp; StackCookie
0x140035592  call    __security_check_cookie
0x140035597  lea     r11, [rsp+1D0h+var_s0]
0x14003559f  mov     rbx, [r11+18h]
0x1400355a3  mov     rdi, [r11+20h]
0x1400355a7  mov     rsp, r11
0x1400355aa  pop     rbp
0x1400355ab  retn
0x1400355ad  call    cs:__imp_GetLastError
0x1400355b4  nop     dword ptr [rax+rax+00h]
0x1400355b9  nop
0x1400355ba  mov     rcx, [rbp+0D8h]; this
0x1400355c1  lea     rdx, aFailedToSetIma; "Failed to set image mitigation policy o"...
0x1400355c8  mov     qword ptr [rsp+1D0h+dwAuthnLevel], rdx; unsigned int
0x1400355cd  mov     r9d, eax; char *
0x1400355d0  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\refsdedupsvc\\exe\\r"...
0x1400355d7  mov     edx, 63h ; 'c'; void *
0x1400355dc  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1400355e2  lea     r8, aOnecoreBaseFsR_13; "onecore\\base\\fs\\refsdedupsvc\\SvcLib"...
0x1400355e9  mov     edx, 0A3h; void *
0x1400355ee  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400355f4  mov     r9d, eax; char *
0x1400355f7  lea     r8, aOnecoreBaseFsR_3; "onecore\\base\\fs\\refsdedupsvc\\exe\\r"...
0x1400355fe  mov     edx, 3Ch ; '<'; void *
0x140035603  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
