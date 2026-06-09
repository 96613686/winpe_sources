# DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)

- ea: `0x18000c384`
- end: `0x18000c424`
- name: `?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z`
- size: `160`
- prototype: `signed int __fastcall(SERVICE_STATUS_HANDLE *this, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000bac8`
- `0x18000c4a0`

## callees

- `0x1800020c0`
- `0x18000c384`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3f6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c3e8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c3e8`

## pseudocode

```c
signed int __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(
        SERVICE_STATUS_HANDLE *this,
        DWORD a2)
{
  DWORD v2; // r8d
  signed int result; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = 0;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwServiceType = 48;
  ServiceStatus.dwCurrentState = a2;
  if ( a2 == 4 )
  {
    ServiceStatus.dwControlsAccepted = 5;
  }
  else
  {
    if ( a2 - 2 <= 1 )
      v2 = 500;
    ServiceStatus.dwWaitHint = v2;
  }
  if ( SetServiceStatus(*this, &ServiceStatus) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x18000c384  sub     rsp, 58h
0x18000c388  mov     rax, cs:__security_cookie
0x18000c38f  xor     rax, rsp
0x18000c392  mov     [rsp+58h+var_18], rax
0x18000c397  xor     r8d, r8d
0x18000c39a  mov     qword ptr [rsp+58h+ServiceStatus.dwControlsAccepted], 0
0x18000c3a3  mov     qword ptr [rsp+58h+ServiceStatus.dwServiceSpecificExitCode], 0
0x18000c3ac  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x18000c3b1  mov     [rsp+58h+ServiceStatus.dwServiceType], 30h ; '0'
0x18000c3b9  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x18000c3bd  cmp     edx, 4
0x18000c3c0  jnz     short loc_18000C3CC
0x18000c3c2  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 5
0x18000c3ca  jmp     short loc_18000C3E0
0x18000c3cc  lea     eax, [rdx-2]
0x18000c3cf  mov     edx, 1F4h
0x18000c3d4  cmp     eax, 1
0x18000c3d7  cmovbe  r8d, edx
0x18000c3db  mov     [rsp+58h+ServiceStatus.dwWaitHint], r8d
0x18000c3e0  mov     rcx, [rcx]; hServiceStatus
0x18000c3e3  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18000c3e8  call    cs:__imp_SetServiceStatus
0x18000c3ee  test    eax, eax
0x18000c3f0  jz      short loc_18000C3F6
0x18000c3f2  xor     eax, eax
0x18000c3f4  jmp     short loc_18000C412
0x18000c3f6  call    cs:__imp_GetLastError
0x18000c3fc  test    eax, eax
0x18000c3fe  jle     short loc_18000C408
0x18000c400  movzx   eax, ax
0x18000c403  or      eax, 80070000h
0x18000c408  test    eax, eax
0x18000c40a  mov     ecx, 80004005h
0x18000c40f  cmovns  eax, ecx
0x18000c412  mov     rcx, [rsp+58h+var_18]
0x18000c417  xor     rcx, rsp; StackCookie
0x18000c41a  call    __security_check_cookie
0x18000c41f  add     rsp, 58h
0x18000c423  retn
```
