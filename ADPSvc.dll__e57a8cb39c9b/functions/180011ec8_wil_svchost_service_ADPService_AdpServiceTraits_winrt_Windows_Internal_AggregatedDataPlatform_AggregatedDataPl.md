# wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)

- ea: `0x180011ec8`
- end: `0x180011f6a`
- name: `?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000ff90`
- `0x18001195c`
- `0x180011b50`

## callees

- `0x180002250`
- `0x180011e68`
- `0x180011ec8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011f44`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011f44`

## string_xrefs

- `0x180011f26`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
        __int64 a1,
        DWORD a2,
        DWORD a3)
{
  SERVICE_STATUS_HANDLE v3; // rcx
  BOOL result; // eax
  const struct winrt::impl::slim_source_location *v5; // rdx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  const char *v7; // [rsp+28h] [rbp-38h]
  __int64 v8; // [rsp+30h] [rbp-30h]
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
  v7 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v6 = 422;
  v8 = 0;
  result = SetServiceStatus(v3, &ServiceStatus);
  if ( !result )
    winrt::throw_last_error((winrt *)&v6, v5);
  return result;
}

```

## disassembly

```asm
0x180011ec8  push    rbp
0x180011eca  mov     rbp, rsp
0x180011ecd  sub     rsp, 60h
0x180011ed1  mov     rax, cs:__security_cookie
0x180011ed8  xor     rax, rsp
0x180011edb  mov     [rbp+var_8], rax
0x180011edf  xor     eax, eax
0x180011ee1  mov     [rbp+ServiceStatus.dwServiceType], 60h ; '`'
0x180011ee8  mov     [rbp+ServiceStatus.dwCurrentState], edx
0x180011eeb  xorps   xmm0, xmm0
0x180011eee  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x180011ef1  movups  xmmword ptr [rbp+ServiceStatus.dwControlsAccepted], xmm0
0x180011ef5  mov     [rbp+ServiceStatus.dwWin32ExitCode], r8d
0x180011ef9  cmp     edx, 4
0x180011efc  jz      short loc_180011F1B
0x180011efe  cmp     edx, 1
0x180011f01  jz      short loc_180011F1B
0x180011f03  mov     eax, 1
0x180011f08  lock xadd [rcx+28h], eax
0x180011f0d  inc     eax
0x180011f0f  mov     [rbp+ServiceStatus.dwWaitHint], 1388h
0x180011f16  mov     [rbp+ServiceStatus.dwCheckPoint], eax
0x180011f19  jmp     short loc_180011F22
0x180011f1b  mov     [rbp+ServiceStatus.dwControlsAccepted], 401h
0x180011f22  mov     rcx, [rcx+20h]; hServiceStatus
0x180011f26  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x180011f2d  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180011f31  mov     [rbp+var_38], rax
0x180011f35  mov     [rbp+var_40], 1A6h
0x180011f3c  mov     [rbp+var_30], 0
0x180011f44  call    cs:__imp_SetServiceStatus
0x180011f4a  test    eax, eax
0x180011f4c  jz      short loc_180011F60
0x180011f4e  mov     rcx, [rbp+var_8]
0x180011f52  xor     rcx, rsp; StackCookie
0x180011f55  call    __security_check_cookie
0x180011f5a  add     rsp, 60h
0x180011f5e  pop     rbp
0x180011f5f  retn
0x180011f60  lea     rcx, [rbp+var_40]; this
0x180011f64  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
