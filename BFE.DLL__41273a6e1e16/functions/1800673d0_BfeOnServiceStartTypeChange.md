# BfeOnServiceStartTypeChange

- ea: `0x1800673d0`
- end: `0x1800674c7`
- name: `BfeOnServiceStartTypeChange`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180012d8c`
- `0x180055fa4`
- `0x180056028`
- `0x180067090`
- `0x1800672c8`
- `0x1800673d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067455`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800673fd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800673fd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180067441`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180067441`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180067496`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800674a5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180067496`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800674a5`

## string_xrefs

- `0x180067420`: `OpenSCManagerW`
- `0x180067464`: `OpenServiceW`

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
0x1800673d0  mov     [rsp+arg_8], rbx
0x1800673d5  mov     [rsp+arg_10], rsi
0x1800673da  push    rdi
0x1800673db  sub     rsp, 20h
0x1800673df  mov     [rsp+28h+arg_0], 0
0x1800673e7  call    WfpMemInit
0x1800673ec  test    rax, rax
0x1800673ef  jnz     loc_1800674B6
0x1800673f5  xor     edx, edx; lpDatabaseName
0x1800673f7  lea     r8d, [rax+5]; dwDesiredAccess
0x1800673fb  xor     ecx, ecx; lpMachineName
0x1800673fd  call    cs:__imp_OpenSCManagerW
0x180067404  nop     dword ptr [rax+rax+00h]
0x180067409  mov     rbx, rax
0x18006740c  test    rax, rax
0x18006740f  jnz     short loc_180067431
0x180067411  call    cs:__imp_GetLastError
0x180067418  nop     dword ptr [rax+rax+00h]
0x18006741d  mov     r8d, eax
0x180067420  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x180067427  call    WfpReportSysErrorAsWinError
0x18006742c  jmp     loc_1800674B1
0x180067431  mov     r8d, 1; dwDesiredAccess
0x180067437  lea     rdx, ServiceName; "BFE"
0x18006743e  mov     rcx, rbx; hSCManager
0x180067441  call    cs:__imp_OpenServiceW
0x180067448  nop     dword ptr [rax+rax+00h]
0x18006744d  mov     rdi, rax
0x180067450  test    rax, rax
0x180067453  jnz     short loc_180067472
0x180067455  call    cs:__imp_GetLastError
0x18006745c  nop     dword ptr [rax+rax+00h]
0x180067461  mov     r8d, eax
0x180067464  lea     rdx, aOpenservicew_0; "OpenServiceW"
0x18006746b  call    WfpReportSysErrorAsWinError
0x180067470  jmp     short loc_1800674A2
0x180067472  lea     rdx, [rsp+28h+arg_0]
0x180067477  mov     rcx, rdi; hService
0x18006747a  call    BfeFwTriggerGetServiceStartType
0x18006747f  test    rax, rax
0x180067482  jnz     short loc_180067493
0x180067484  cmp     [rsp+28h+arg_0], 2
0x180067489  jz      short loc_180067493
0x18006748b  mov     rcx, rbx; hSCManager
0x18006748e  call    BfeFwTriggerChangeServicesStartTypeToAuto
0x180067493  mov     rcx, rdi; hSCObject
0x180067496  call    cs:__imp_CloseServiceHandle
0x18006749d  nop     dword ptr [rax+rax+00h]
0x1800674a2  mov     rcx, rbx; hSCObject
0x1800674a5  call    cs:__imp_CloseServiceHandle
0x1800674ac  nop     dword ptr [rax+rax+00h]
0x1800674b1  call    WfpMemShutdown
0x1800674b6  mov     rbx, [rsp+28h+arg_8]
0x1800674bb  mov     rsi, [rsp+28h+arg_10]
0x1800674c0  add     rsp, 20h
0x1800674c4  pop     rdi
0x1800674c5  retn
```
