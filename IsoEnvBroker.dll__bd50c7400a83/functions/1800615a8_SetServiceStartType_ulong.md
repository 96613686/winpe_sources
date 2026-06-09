# SetServiceStartType(ulong)

- ea: `0x1800615a8`
- end: `0x1800617df`
- name: `?SetServiceStartType@@YAJK@Z`
- size: `567`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023170`
- `0x180041b64`
- `0x1800507a8`
- `0x180056060`
- `0x180059200`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x180011e18`
- `0x1800615a8`
- `0x180064360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800615fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800616b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800615fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800616b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061792`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180061636`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180061636`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800615e7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800615e7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800616de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800617a7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800617b2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800616de`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800617a7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800617b2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800616a8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800616a8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180061788`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180061788`

## string_xrefs

- `0x18006162c`: `IsoEnvBroker`
- `0x180061722`: `SERVICE_AUTO_START`
- `0x180061719`: `SERVICE_DEMAND_START`
- `0x180061654`: `Error: Could not open service. Error code: %#x`
- `0x180061710`: `SERVICE_DISABLED`
- `0x180061798`: `Error: Could not change service config: %#x`
- `0x1800616b8`: `Error: Could not query service config. Error code: %#x`
- `0x18006172c`: `Changing service start type to %s (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetServiceStartType(DWORD a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  __int64 LastError; // rbx
  SC_HANDLE v5; // rdi
  DWORD v6; // eax
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-2038h] BYREF
  SC_HANDLE v11; // [rsp+68h] [rbp-2030h]
  SC_HANDLE v12; // [rsp+70h] [rbp-2028h]
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+80h] [rbp-2018h] BYREF

  v11 = 0;
  v2 = OpenSCManagerW(0, 0, 0x40000000u);
  v3 = v2;
  v12 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"IsoEnvBroker", 0xF01FFu);
    v11 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      Log(2u, L"Error: Could not open service. Error code: %#x", LastError);
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_25;
    }
    memset_0(&ServiceConfig, 0, 0x2000u);
    pcbBytesNeeded = 0;
    if ( QueryServiceConfigW(v5, &ServiceConfig, 0x2000u, &pcbBytesNeeded) )
    {
      if ( ServiceConfig.dwStartType == a1
        || (a1 == 2
          ? (v8 = L"SERVICE_AUTO_START")
          : a1 == 3
          ? (v8 = L"SERVICE_DEMAND_START")
          : a1 == 4
          ? (v8 = L"SERVICE_DISABLED")
          : (v8 = L"UNKNOWN_START_TYPE"),
            Log(4u, L"Changing service start type to %s (%d)", v8, a1),
            ChangeServiceConfigW(v5, 0xFFFFFFFF, a1, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)) )
      {
        CloseServiceHandle(v5);
        LODWORD(LastError) = 0;
LABEL_25:
        CloseServiceHandle(v3);
        return (unsigned int)LastError;
      }
      v6 = GetLastError();
      v7 = L"Error: Could not change service config: %#x";
    }
    else
    {
      v6 = GetLastError();
      v7 = L"Error: Could not query service config. Error code: %#x";
    }
    LODWORD(LastError) = v6;
    Log(2u, v7, v6);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    CloseServiceHandle(v5);
    goto LABEL_25;
  }
  LastError = GetLastError();
  Log(2u, L"Unable to get a handle on the SCM: %#x", LastError);
  if ( (int)LastError > 0 )
    LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800615a8  mov     [rsp+arg_8], rbx
0x1800615ad  mov     [rsp+arg_10], rsi
0x1800615b2  push    rdi
0x1800615b3  mov     eax, 2090h
0x1800615b8  call    _alloca_probe
0x1800615bd  sub     rsp, rax
0x1800615c0  mov     rax, cs:__security_cookie
0x1800615c7  xor     rax, rsp
0x1800615ca  mov     [rsp+2098h+var_18], rax
0x1800615d2  mov     ebx, ecx
0x1800615d4  mov     [rsp+2098h+var_2030], 0
0x1800615dd  xor     edx, edx; lpDatabaseName
0x1800615df  xor     ecx, ecx; lpMachineName
0x1800615e1  mov     r8d, 40000000h; dwDesiredAccess
0x1800615e7  call    cs:__imp_OpenSCManagerW
0x1800615ed  mov     rsi, rax
0x1800615f0  mov     [rsp+2098h+var_2028], rax
0x1800615f5  test    rax, rax
0x1800615f8  jnz     short loc_180061626
0x1800615fa  call    cs:__imp_GetLastError
0x180061600  mov     ebx, eax
0x180061602  mov     r8d, eax
0x180061605  lea     rdx, aUnableToGetAHa; "Unable to get a handle on the SCM: %#x"
0x18006160c  lea     ecx, [rsi+2]; unsigned __int8
0x18006160f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180061614  test    ebx, ebx
0x180061616  jle     short loc_180061621
0x180061618  movzx   ebx, bx
0x18006161b  or      ebx, 80070000h
0x180061621  jmp     loc_1800617B8
0x180061626  mov     r8d, 0F01FFh; dwDesiredAccess
0x18006162c  lea     rdx, ServiceName; "IsoEnvBroker"
0x180061633  mov     rcx, rsi; hSCManager
0x180061636  call    cs:__imp_OpenServiceW
0x18006163c  mov     rdi, rax
0x18006163f  mov     [rsp+2098h+var_2030], rax
0x180061644  test    rax, rax
0x180061647  jnz     short loc_180061675
0x180061649  call    cs:__imp_GetLastError
0x18006164f  mov     ebx, eax
0x180061651  mov     r8d, eax
0x180061654  lea     rdx, aErrorCouldNotO; "Error: Could not open service. Error co"...
0x18006165b  lea     ecx, [rdi+2]; unsigned __int8
0x18006165e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180061663  test    ebx, ebx
0x180061665  jle     short loc_180061670
0x180061667  movzx   ebx, bx
0x18006166a  or      ebx, 80070000h
0x180061670  jmp     loc_1800617AF
0x180061675  xor     edx, edx; Val
0x180061677  mov     r8d, 2000h; Size
0x18006167d  lea     rcx, [rsp+2098h+ServiceConfig]; void *
0x180061685  call    memset_0
0x18006168a  mov     [rsp+2098h+pcbBytesNeeded], 0
0x180061692  lea     r9, [rsp+2098h+pcbBytesNeeded]; pcbBytesNeeded
0x180061697  mov     r8d, 2000h; cbBufSize
0x18006169d  lea     rdx, [rsp+2098h+ServiceConfig]; lpServiceConfig
0x1800616a5  mov     rcx, rdi; hService
0x1800616a8  call    cs:__imp_QueryServiceConfigW
0x1800616ae  test    eax, eax
0x1800616b0  jnz     short loc_1800616E9
0x1800616b2  call    cs:__imp_GetLastError
0x1800616b8  lea     rdx, aErrorCouldNotQ; "Error: Could not query service config. "...
0x1800616bf  mov     ebx, eax
0x1800616c1  mov     r8d, eax
0x1800616c4  mov     ecx, 2; unsigned __int8
0x1800616c9  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800616ce  test    ebx, ebx
0x1800616d0  jle     short loc_1800616DB
0x1800616d2  movzx   ebx, bx
0x1800616d5  or      ebx, 80070000h
0x1800616db  mov     rcx, rdi; hSCObject
0x1800616de  call    cs:__imp_CloseServiceHandle
0x1800616e4  jmp     loc_1800617AF
0x1800616e9  cmp     [rsp+2098h+ServiceConfig.dwStartType], ebx
0x1800616f0  jz      loc_1800617A4
0x1800616f6  mov     eax, ebx
0x1800616f8  sub     eax, 2
0x1800616fb  jz      short loc_180061722
0x1800616fd  sub     eax, 1
0x180061700  jz      short loc_180061719
0x180061702  cmp     eax, 1
0x180061705  jz      short loc_180061710
0x180061707  lea     r8, aUnknownStartTy; "UNKNOWN_START_TYPE"
0x18006170e  jmp     short loc_180061729
0x180061710  lea     r8, aServiceDisable; "SERVICE_DISABLED"
0x180061717  jmp     short loc_180061729
0x180061719  lea     r8, aServiceDemandS; "SERVICE_DEMAND_START"
0x180061720  jmp     short loc_180061729
0x180061722  lea     r8, aServiceAutoSta; "SERVICE_AUTO_START"
0x180061729  mov     r9d, ebx
0x18006172c  lea     rdx, aChangingServic; "Changing service start type to %s (%d)"
0x180061733  mov     ecx, 4; unsigned __int8
0x180061738  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18006173d  mov     [rsp+2098h+lpDisplayName], 0; lpDisplayName
0x180061746  mov     [rsp+2098h+lpPassword], 0; lpPassword
0x18006174f  mov     [rsp+2098h+lpServiceStartName], 0; lpServiceStartName
0x180061758  mov     [rsp+2098h+lpDependencies], 0; lpDependencies
0x180061761  mov     [rsp+2098h+lpdwTagId], 0; lpdwTagId
0x18006176a  mov     [rsp+2098h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180061773  mov     [rsp+2098h+lpBinaryPathName], 0; lpBinaryPathName
0x18006177c  or      edx, 0FFFFFFFFh; dwServiceType
0x18006177f  mov     r9d, edx; dwErrorControl
0x180061782  mov     r8d, ebx; dwStartType
0x180061785  mov     rcx, rdi; hService
0x180061788  call    cs:__imp_ChangeServiceConfigW
0x18006178e  test    eax, eax
0x180061790  jnz     short loc_1800617A4
0x180061792  call    cs:__imp_GetLastError
0x180061798  lea     rdx, aErrorCouldNotC; "Error: Could not change service config:"...
0x18006179f  jmp     loc_1800616BF
0x1800617a4  mov     rcx, rdi; hSCObject
0x1800617a7  call    cs:__imp_CloseServiceHandle
0x1800617ad  xor     ebx, ebx
0x1800617af  mov     rcx, rsi; hSCObject
0x1800617b2  call    cs:__imp_CloseServiceHandle
0x1800617b8  mov     eax, ebx
0x1800617ba  mov     rcx, [rsp+2098h+var_18]
0x1800617c2  xor     rcx, rsp; StackCookie
0x1800617c5  call    __security_check_cookie
0x1800617ca  lea     r11, [rsp+2098h+var_8]
0x1800617d2  mov     rbx, [r11+18h]
0x1800617d6  mov     rsi, [r11+20h]
0x1800617da  mov     rsp, r11
0x1800617dd  pop     rdi
0x1800617de  retn
```
