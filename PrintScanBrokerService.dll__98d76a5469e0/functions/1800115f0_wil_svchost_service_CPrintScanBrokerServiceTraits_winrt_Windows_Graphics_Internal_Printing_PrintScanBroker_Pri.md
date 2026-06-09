# wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::update_status(ulong,ulong)

- ea: `0x1800115f0`
- end: `0x180011684`
- name: `?update_status@?$svchost_service@UCPrintScanBrokerServiceTraits@@UPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@UVirtualPrinterInstallerBroker@345678@UIppQueuePropertyBagHandler@345678@@wil@@AEAAXKK@Z`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fc48`
- `0x180010f90`
- `0x180011104`

## callees

- `0x180002d40`
- `0x180011428`
- `0x1800115f0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001165e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001165e`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<CPrintScanBrokerServiceTraits,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::PrintScanBrokerHandler,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::VirtualPrinterInstallerBroker,winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::IppQueuePropertyBagHandler>::update_status(
        __int64 a1,
        DWORD a2,
        DWORD a3)
{
  SERVICE_STATUS_HANDLE v3; // rcx
  BOOL result; // eax
  const struct winrt::impl::slim_source_location *v5; // rdx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  __int128 v7; // [rsp+28h] [rbp-38h]
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ServiceStatus.dwServiceType = 96;
  ServiceStatus.dwCurrentState = a2;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwWin32ExitCode = a3;
  if ( a2 == 4 || a2 == 1 )
  {
    ServiceStatus.dwControlsAccepted = 1025;
  }
  else
  {
    ServiceStatus.dwWaitHint = 5000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  }
  v3 = *(SERVICE_STATUS_HANDLE *)(a1 + 32);
  v6 = 0;
  v7 = 0;
  result = SetServiceStatus(v3, &ServiceStatus);
  if ( !result )
    winrt::throw_last_error((winrt *)&v6, v5);
  return result;
}

```

## disassembly

```asm
0x1800115f0  push    rbp
0x1800115f2  mov     rbp, rsp
0x1800115f5  sub     rsp, 60h
0x1800115f9  mov     rax, cs:__security_cookie
0x180011600  xor     rax, rsp
0x180011603  mov     [rbp+var_8], rax
0x180011607  xor     eax, eax
0x180011609  mov     [rbp+ServiceStatus.dwServiceType], 60h ; '`'
0x180011610  mov     [rbp+ServiceStatus.dwCurrentState], edx
0x180011613  xorps   xmm0, xmm0
0x180011616  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x180011619  movups  xmmword ptr [rbp+ServiceStatus.dwControlsAccepted], xmm0
0x18001161d  mov     [rbp+ServiceStatus.dwWin32ExitCode], r8d
0x180011621  cmp     edx, 4
0x180011624  jz      short loc_180011643
0x180011626  cmp     edx, 1
0x180011629  jz      short loc_180011643
0x18001162b  mov     eax, 1
0x180011630  lock xadd [rcx+28h], eax
0x180011635  inc     eax
0x180011637  mov     [rbp+ServiceStatus.dwWaitHint], 1388h
0x18001163e  mov     [rbp+ServiceStatus.dwCheckPoint], eax
0x180011641  jmp     short loc_18001164A
0x180011643  mov     [rbp+ServiceStatus.dwControlsAccepted], 401h
0x18001164a  mov     rcx, [rcx+20h]; hServiceStatus
0x18001164e  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180011652  mov     [rbp+var_40], 0
0x180011659  movdqu  [rbp+var_38], xmm0
0x18001165e  call    cs:__imp_SetServiceStatus
0x180011664  test    eax, eax
0x180011666  jz      short loc_18001167A
0x180011668  mov     rcx, [rbp+var_8]
0x18001166c  xor     rcx, rsp; StackCookie
0x18001166f  call    __security_check_cookie
0x180011674  add     rsp, 60h
0x180011678  pop     rbp
0x180011679  retn
0x18001167a  lea     rcx, [rbp+var_40]; this
0x18001167e  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
