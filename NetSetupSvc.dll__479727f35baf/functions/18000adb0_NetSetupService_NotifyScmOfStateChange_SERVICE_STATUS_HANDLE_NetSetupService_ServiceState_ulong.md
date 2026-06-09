# NetSetupService::NotifyScmOfStateChange(SERVICE_STATUS_HANDLE__ *,NetSetupService::ServiceState,ulong)

- ea: `0x18000adb0`
- end: `0x18000ae42`
- name: `?NotifyScmOfStateChange@NetSetupService@@CA_NPEAUSERVICE_STATUS_HANDLE__@@W4ServiceState@1@K@Z`
- size: `146`
- prototype: `bool __fastcall(SERVICE_STATUS_HANDLE, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000affc`
- `0x18000cf2c`

## callees

- `0x1800027c0`
- `0x18000adb0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ae25`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ae25`

## pseudocode

```c
bool __fastcall NetSetupService::NotifyScmOfStateChange(SERVICE_STATUS_HANDLE a1, int a2)
{
  bool result; // al
  int v3; // edx
  int v4; // edx
  int v5; // edx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  result = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          if ( v5 != 1 )
            return result;
          ServiceStatus.dwCurrentState = 1;
        }
        else
        {
          ServiceStatus.dwCurrentState = 3;
        }
      }
      else
      {
        ServiceStatus.dwCurrentState = 4;
        ServiceStatus.dwControlsAccepted = 1;
      }
    }
    else
    {
      ServiceStatus.dwCurrentState = 2;
    }
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwWin32ExitCode = 0;
    return SetServiceStatus(a1, &ServiceStatus);
  }
  return result;
}

```

## disassembly

```asm
0x18000adb0  sub     rsp, 58h
0x18000adb4  mov     rax, cs:__security_cookie
0x18000adbb  xor     rax, rsp
0x18000adbe  mov     [rsp+58h+var_18], rax
0x18000adc3  xorps   xmm0, xmm0
0x18000adc6  xor     eax, eax
0x18000adc8  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18000adcd  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000add2  test    edx, edx
0x18000add4  jz      short loc_18000AE30
0x18000add6  sub     edx, 1
0x18000add9  jz      short loc_18000AE0C
0x18000addb  sub     edx, 1
0x18000adde  jz      short loc_18000ADFA
0x18000ade0  sub     edx, 1
0x18000ade3  jz      short loc_18000ADF0
0x18000ade5  cmp     edx, 1
0x18000ade8  jnz     short loc_18000AE30
0x18000adea  mov     [rsp+58h+ServiceStatus.dwCurrentState], edx
0x18000adee  jmp     short loc_18000AE14
0x18000adf0  mov     [rsp+58h+ServiceStatus.dwCurrentState], 3
0x18000adf8  jmp     short loc_18000AE14
0x18000adfa  mov     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18000ae02  mov     [rsp+58h+ServiceStatus.dwControlsAccepted], 1
0x18000ae0a  jmp     short loc_18000AE14
0x18000ae0c  mov     [rsp+58h+ServiceStatus.dwCurrentState], 2
0x18000ae14  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18000ae19  mov     [rsp+58h+ServiceStatus.dwServiceType], 20h ; ' '
0x18000ae21  mov     [rsp+58h+ServiceStatus.dwWin32ExitCode], eax
0x18000ae25  call    cs:__imp_SetServiceStatus
0x18000ae2b  test    eax, eax
0x18000ae2d  setnz   al
0x18000ae30  mov     rcx, [rsp+58h+var_18]
0x18000ae35  xor     rcx, rsp; StackCookie
0x18000ae38  call    __security_check_cookie
0x18000ae3d  add     rsp, 58h
0x18000ae41  retn
```
