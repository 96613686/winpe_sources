# NetSetupService::~NetSetupService(void)

- ea: `0x1800091c0`
- end: `0x180009260`
- name: `??1NetSetupService@@QEAA@XZ`
- size: `160`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800072f8`

## callees

- `0x180008de0`
- `0x180008e20`
- `0x180008e3c`
- `0x1800091c0`
- `0x180009268`
- `0x1800092ec`
- `0x18000d04c`
- `0x18001d74c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800091e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800091e3`

## pseudocode

```c
void __fastcall NetSetupService::~NetSetupService(HKEY *this)
{
  DWORD v2; // ecx

  if ( (unsigned int)(*((_DWORD *)this + 30) - 1) <= 2 )
    NetSetupService::StopSubsystems((NetSetupService *)this);
  v2 = *((_DWORD *)this + 91);
  if ( v2 != -1 )
  {
    TlsFree(v2);
    *((_DWORD *)this + 91) = -1;
  }
  this[12] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this + 37);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this + 36);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this + 35);
  QueuedServiceControl::~QueuedServiceControl((QueuedServiceControl *)(this + 28));
  NetSetupSvcDeviceManager::~NetSetupSvcDeviceManager((NetSetupSvcDeviceManager *)(this + 21));
  std::unique_ptr<void,SafeHandleCleanupIsUnregisterWait>::~unique_ptr<void,SafeHandleCleanupIsUnregisterWait>(this + 14);
  std::unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>::~unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>(this + 13);
  std::unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>::~unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>(this + 11);
  NetSetupSvcTransactionCoordinator::~NetSetupSvcTransactionCoordinator((NetSetupSvcTransactionCoordinator *)(this + 4));
}

```

## disassembly

```asm
0x1800091c0  push    rbx
0x1800091c2  sub     rsp, 20h
0x1800091c6  mov     eax, [rcx+78h]
0x1800091c9  mov     rbx, rcx
0x1800091cc  dec     eax
0x1800091ce  cmp     eax, 2
0x1800091d1  ja      short loc_1800091D8
0x1800091d3  call    ?StopSubsystems@NetSetupService@@AEAAXXZ; NetSetupService::StopSubsystems(void)
0x1800091d8  mov     ecx, [rbx+16Ch]; dwTlsIndex
0x1800091de  cmp     ecx, 0FFFFFFFFh
0x1800091e1  jz      short loc_1800091F3
0x1800091e3  call    cs:__imp_TlsFree
0x1800091e9  mov     dword ptr [rbx+16Ch], 0FFFFFFFFh
0x1800091f3  lea     rcx, [rbx+128h]
0x1800091fa  mov     qword ptr [rbx+60h], 0
0x180009202  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009207  lea     rcx, [rbx+120h]
0x18000920e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009213  lea     rcx, [rbx+118h]
0x18000921a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000921f  lea     rcx, [rbx+0E0h]; this
0x180009226  call    ??1QueuedServiceControl@@QEAA@XZ; QueuedServiceControl::~QueuedServiceControl(void)
0x18000922b  lea     rcx, [rbx+0A8h]; this
0x180009232  call    ??1NetSetupSvcDeviceManager@@QEAA@XZ; NetSetupSvcDeviceManager::~NetSetupSvcDeviceManager(void)
0x180009237  lea     rcx, [rbx+70h]
0x18000923b  call    ??1?$unique_ptr@XUSafeHandleCleanupIsUnregisterWait@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupIsUnregisterWait>::~unique_ptr<void,SafeHandleCleanupIsUnregisterWait>(void)
0x180009240  lea     rcx, [rbx+68h]
0x180009244  call    ??1?$unique_ptr@XU?$SafeHandleCleanupWithCloseHandle@USafeHandleNullIsInvalid@@@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>::~unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>(void)
0x180009249  lea     rcx, [rbx+58h]
0x18000924d  call    ??1?$unique_ptr@XU?$SafeHandleCleanupWithCloseHandle@USafeHandleNullIsInvalid@@@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>::~unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullIsInvalid>>(void)
0x180009252  lea     rcx, [rbx+20h]; this
0x180009256  add     rsp, 20h
0x18000925a  pop     rbx
0x18000925b  jmp     ??1NetSetupSvcTransactionCoordinator@@QEAA@XZ; NetSetupSvcTransactionCoordinator::~NetSetupSvcTransactionCoordinator(void)
```
