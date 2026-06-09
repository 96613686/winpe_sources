# BfeOnServiceStartTypeChange

- ea: `0x180064fd0`
- end: `0x18006509f`
- name: `BfeOnServiceStartTypeChange`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18001236c`
- `0x180054188`
- `0x180054204`
- `0x180064cd4`
- `0x180064edc`
- `0x180064fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006500b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006500b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065040`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180064ffd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180064ffd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180065032`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180065032`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006507b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180065084`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006507b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180065084`

## string_xrefs

- `0x180065014`: `OpenSCManagerW`
- `0x180065049`: `OpenServiceW`

## pseudocode

```c
__int64 BfeOnServiceStartTypeChange()
{
  __int64 result; // rax
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  DWORD v3; // eax
  __int64 v4; // rcx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx

  result = WfpMemInit();
  if ( !result )
  {
    v1 = OpenSCManagerW(0, 0, 5u);
    v2 = v1;
    if ( v1 )
    {
      v5 = OpenServiceW(v1, L"BFE", 1u);
      v6 = v5;
      if ( v5 )
      {
        if ( !BfeFwTriggerGetServiceStartType(v5) )
          BfeFwTriggerChangeServicesStartTypeToAuto(v2);
        CloseServiceHandle(v6);
      }
      else
      {
        LastError = GetLastError();
        WfpReportSysErrorAsWinError(v8, "OpenServiceW", LastError);
      }
      CloseServiceHandle(v2);
    }
    else
    {
      v3 = GetLastError();
      WfpReportSysErrorAsWinError(v4, "OpenSCManagerW", v3);
    }
    return WfpMemShutdown();
  }
  return result;
}

```

## disassembly

```asm
0x180064fd0  mov     [rsp+arg_8], rbx
0x180064fd5  mov     [rsp+arg_10], rsi
0x180064fda  push    rdi
0x180064fdb  sub     rsp, 20h
0x180064fdf  mov     [rsp+28h+arg_0], 0
0x180064fe7  call    WfpMemInit
0x180064fec  test    rax, rax
0x180064fef  jnz     loc_18006508F
0x180064ff5  xor     edx, edx; lpDatabaseName
0x180064ff7  lea     r8d, [rax+5]; dwDesiredAccess
0x180064ffb  xor     ecx, ecx; lpMachineName
0x180064ffd  call    cs:__imp_OpenSCManagerW
0x180065003  mov     rbx, rax
0x180065006  test    rax, rax
0x180065009  jnz     short loc_180065022
0x18006500b  call    cs:__imp_GetLastError
0x180065011  mov     r8d, eax
0x180065014  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x18006501b  call    WfpReportSysErrorAsWinError
0x180065020  jmp     short loc_18006508A
0x180065022  mov     r8d, 1; dwDesiredAccess
0x180065028  lea     rdx, ServiceName; "BFE"
0x18006502f  mov     rcx, rbx; hSCManager
0x180065032  call    cs:__imp_OpenServiceW
0x180065038  mov     rdi, rax
0x18006503b  test    rax, rax
0x18006503e  jnz     short loc_180065057
0x180065040  call    cs:__imp_GetLastError
0x180065046  mov     r8d, eax
0x180065049  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x180065050  call    WfpReportSysErrorAsWinError
0x180065055  jmp     short loc_180065081
0x180065057  lea     rdx, [rsp+28h+arg_0]
0x18006505c  mov     rcx, rdi; hService
0x18006505f  call    BfeFwTriggerGetServiceStartType
0x180065064  test    rax, rax
0x180065067  jnz     short loc_180065078
0x180065069  cmp     [rsp+28h+arg_0], 2
0x18006506e  jz      short loc_180065078
0x180065070  mov     rcx, rbx; hSCManager
0x180065073  call    BfeFwTriggerChangeServicesStartTypeToAuto
0x180065078  mov     rcx, rdi; hSCObject
0x18006507b  call    cs:__imp_CloseServiceHandle
0x180065081  mov     rcx, rbx; hSCObject
0x180065084  call    cs:__imp_CloseServiceHandle
0x18006508a  call    WfpMemShutdown
0x18006508f  mov     rbx, [rsp+28h+arg_8]
0x180065094  mov     rsi, [rsp+28h+arg_10]
0x180065099  add     rsp, 20h
0x18006509d  pop     rdi
0x18006509e  retn
```
