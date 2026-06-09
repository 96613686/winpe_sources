# Int_FwStartFirewallService

- ea: `0x18000e460`
- end: `0x18000e740`
- name: `Int_FwStartFirewallService`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000d0f0`

## callees

- `0x180005e0c`
- `0x18000e460`
- `0x1800294b0`
- `0x18004c03c`
- `0x18004c0f0`
- `0x180058b7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e4b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6c9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000e5f2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000e5f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e571`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e642`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e651`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e571`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e642`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000e651`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e535`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000e535`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000e4a5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000e4a5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000e599`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000e599`

## string_xrefs

- `0x18000e482`: `ServicesActive`
- `0x18000e6ab`: `OpenSCManager`
- `0x18000e67f`: `OpenService`
- `0x18000e6fd`: `QueryServiceStatus`
- `0x18000e627`: `StartService`
- `0x18000e70b`: `Int_FwStartFirewallService`

## pseudocode

```c
__int64 Int_FwStartFirewallService()
{
  int v0; // ebp
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD LastError; // edi
  int v4; // r8d
  FwPolicy2 *v5; // rcx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r14
  int v9; // r8d
  int v10; // r8d
  FwPolicy2 *v11; // rcx
  int v12; // edx
  const char *v13; // rax
  const char *v14; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v0 = 1;
  v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v2 = v1;
  if ( v1 )
  {
    v7 = OpenServiceW(v1, L"MpsSvc", 0x14u);
    v8 = v7;
    if ( !v7 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 623, v9, LastError, (__int64)"OpenService");
      CloseServiceHandle(v2);
      goto LABEL_12;
    }
    if ( QueryServiceStatus(v7, &ServiceStatus) )
    {
      LastError = 0;
      if ( ServiceStatus.dwCurrentState == 4 )
        goto LABEL_23;
      v0 = 0;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          625,
          WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
          ServiceStatus.dwCurrentState);
      if ( StartServiceW(v8, 0, 0) )
        goto LABEL_23;
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v12 = 626;
      v13 = "StartService";
    }
    else
    {
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_23:
        CloseServiceHandle(v2);
        CloseServiceHandle(v8);
        if ( !v0 )
          FwTelemetryEventManualStart(v14, LastError);
        goto LABEL_12;
      }
      v12 = 624;
      v13 = "QueryServiceStatus";
    }
    WPP_SF_Ds(*((_QWORD *)v11 + 2), v12, v10, LastError, (__int64)v13);
    goto LABEL_23;
  }
  LastError = GetLastError();
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 622, v4, LastError, (__int64)"OpenSCManager");
LABEL_12:
    v5 = WPP_GLOBAL_Control;
  }
  if ( (LastError & 0x80000000) != 0 )
  {
    FwTelemetryEventWriteError("Int_FwStartFirewallService", LastError);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 627, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000e460  push    rdi
0x18000e462  sub     rsp, 60h
0x18000e466  mov     rax, cs:__security_cookie
0x18000e46d  xor     rax, rsp
0x18000e470  mov     [rsp+68h+var_18], rax
0x18000e475  xorps   xmm0, xmm0
0x18000e478  mov     [rsp+68h+arg_0], rbx
0x18000e47d  mov     [rsp+68h+arg_8], rbp
0x18000e482  lea     rdx, DatabaseName; "ServicesActive"
0x18000e489  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18000e48e  mov     ebp, 1
0x18000e493  mov     [rsp+68h+arg_10], rsi
0x18000e49b  mov     r8d, ebp; dwDesiredAccess
0x18000e49e  xor     ecx, ecx; lpMachineName
0x18000e4a0  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000e4a5  call    cs:__imp_OpenSCManagerW
0x18000e4ac  nop     dword ptr [rax+rax+00h]
0x18000e4b1  mov     rsi, rax
0x18000e4b4  test    rax, rax
0x18000e4b7  jnz     short loc_18000E51D
0x18000e4b9  call    cs:__imp_GetLastError
0x18000e4c0  nop     dword ptr [rax+rax+00h]
0x18000e4c5  mov     edi, eax
0x18000e4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4ce  lea     rbx, WPP_GLOBAL_Control
0x18000e4d5  cmp     rcx, rbx
0x18000e4d8  jnz     loc_18000E69D
0x18000e4de  mov     rsi, [rsp+68h+arg_10]
0x18000e4e6  mov     rbp, [rsp+68h+arg_8]
0x18000e4eb  test    edi, edi
0x18000e4ed  js      loc_18000E709
0x18000e4f3  cmp     rcx, rbx
0x18000e4f6  mov     rbx, [rsp+68h+arg_0]
0x18000e4fb  jz      short loc_18000E507
0x18000e4fd  test    byte ptr [rcx+1Ch], 8
0x18000e501  jnz     loc_18000E723
0x18000e507  mov     eax, edi
0x18000e509  mov     rcx, [rsp+68h+var_18]
0x18000e50e  xor     rcx, rsp; StackCookie
0x18000e511  call    __security_check_cookie
0x18000e516  add     rsp, 60h
0x18000e51a  pop     rdi
0x18000e51b  retn
0x18000e51d  mov     r8d, 14h; dwDesiredAccess
0x18000e523  mov     [rsp+68h+arg_18], r14
0x18000e52b  lea     rdx, ServiceName; "MpsSvc"
0x18000e532  mov     rcx, rsi; hSCManager
0x18000e535  call    cs:__imp_OpenServiceW
0x18000e53c  nop     dword ptr [rax+rax+00h]
0x18000e541  mov     r14, rax
0x18000e544  test    rax, rax
0x18000e547  jnz     short loc_18000E591
0x18000e549  call    cs:__imp_GetLastError
0x18000e550  nop     dword ptr [rax+rax+00h]
0x18000e555  mov     edi, eax
0x18000e557  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e55e  lea     rbx, WPP_GLOBAL_Control
0x18000e565  cmp     rcx, rbx
0x18000e568  jnz     loc_18000E671
0x18000e56e  mov     rcx, rsi; hSCObject
0x18000e571  call    cs:__imp_CloseServiceHandle
0x18000e578  nop     dword ptr [rax+rax+00h]
0x18000e57d  mov     r14, [rsp+68h+arg_18]
0x18000e585  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e58c  jmp     loc_18000E4DE
0x18000e591  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18000e596  mov     rcx, r14; hService
0x18000e599  call    cs:__imp_QueryServiceStatus
0x18000e5a0  nop     dword ptr [rax+rax+00h]
0x18000e5a5  test    eax, eax
0x18000e5a7  jz      loc_18000E6C9
0x18000e5ad  mov     r9d, [rsp+68h+ServiceStatus.dwCurrentState]
0x18000e5b2  lea     rbx, WPP_GLOBAL_Control
0x18000e5b9  xor     edi, edi
0x18000e5bb  cmp     r9d, 4
0x18000e5bf  jz      short loc_18000E63F
0x18000e5c1  xor     ebp, ebp
0x18000e5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5ca  cmp     rcx, rbx
0x18000e5cd  jz      short loc_18000E5EA
0x18000e5cf  test    byte ptr [rcx+1Ch], 4
0x18000e5d3  jz      short loc_18000E5EA
0x18000e5d5  mov     rcx, [rcx+10h]
0x18000e5d9  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000e5e0  mov     edx, 271h
0x18000e5e5  call    WPP_SF_d
0x18000e5ea  xor     r8d, r8d; lpServiceArgVectors
0x18000e5ed  xor     edx, edx; dwNumServiceArgs
0x18000e5ef  mov     rcx, r14; hService
0x18000e5f2  call    cs:__imp_StartServiceW
0x18000e5f9  nop     dword ptr [rax+rax+00h]
0x18000e5fe  test    eax, eax
0x18000e600  jnz     short loc_18000E63F
0x18000e602  call    cs:__imp_GetLastError
0x18000e609  nop     dword ptr [rax+rax+00h]
0x18000e60e  mov     edi, eax
0x18000e610  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e617  cmp     rcx, rbx
0x18000e61a  jz      short loc_18000E63F
0x18000e61c  test    byte ptr [rcx+1Ch], 1
0x18000e620  jz      short loc_18000E63F
0x18000e622  mov     edx, 272h
0x18000e627  lea     rax, aStartservice; "StartService"
0x18000e62e  mov     rcx, [rcx+10h]
0x18000e632  mov     r9d, edi
0x18000e635  mov     [rsp+68h+var_48], rax
0x18000e63a  call    WPP_SF_Ds
0x18000e63f  mov     rcx, rsi; hSCObject
0x18000e642  call    cs:__imp_CloseServiceHandle
0x18000e649  nop     dword ptr [rax+rax+00h]
0x18000e64e  mov     rcx, r14; hSCObject
0x18000e651  call    cs:__imp_CloseServiceHandle
0x18000e658  nop     dword ptr [rax+rax+00h]
0x18000e65d  test    ebp, ebp
0x18000e65f  jnz     loc_18000E57D
0x18000e665  mov     edx, edi; unsigned int
0x18000e667  call    ?FwTelemetryEventManualStart@@YAXPEBDI@Z; FwTelemetryEventManualStart(char const *,uint)
0x18000e66c  jmp     loc_18000E57D
0x18000e671  test    [rcx+1Ch], bpl
0x18000e675  jz      loc_18000E56E
0x18000e67b  mov     rcx, [rcx+10h]
0x18000e67f  lea     rax, aOpenservice; "OpenService"
0x18000e686  mov     edx, 26Fh
0x18000e68b  mov     [rsp+68h+var_48], rax
0x18000e690  mov     r9d, edi
0x18000e693  call    WPP_SF_Ds
0x18000e698  jmp     loc_18000E56E
0x18000e69d  test    [rcx+1Ch], bpl
0x18000e6a1  jz      loc_18000E4DE
0x18000e6a7  mov     rcx, [rcx+10h]
0x18000e6ab  lea     rax, aOpenscmanager; "OpenSCManager"
0x18000e6b2  mov     edx, 26Eh
0x18000e6b7  mov     [rsp+68h+var_48], rax
0x18000e6bc  mov     r9d, edi
0x18000e6bf  call    WPP_SF_Ds
0x18000e6c4  jmp     loc_18000E585
0x18000e6c9  call    cs:__imp_GetLastError
0x18000e6d0  nop     dword ptr [rax+rax+00h]
0x18000e6d5  mov     edi, eax
0x18000e6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6de  lea     rbx, WPP_GLOBAL_Control
0x18000e6e5  cmp     rcx, rbx
0x18000e6e8  jz      loc_18000E63F
0x18000e6ee  test    [rcx+1Ch], bpl
0x18000e6f2  jz      loc_18000E63F
0x18000e6f8  mov     edx, 270h
0x18000e6fd  lea     rax, aQueryservicest_0; "QueryServiceStatus"
0x18000e704  jmp     loc_18000E62E
0x18000e709  mov     edx, edi; unsigned int
0x18000e70b  lea     rcx, aIntFwstartfire; "Int_FwStartFirewallService"
0x18000e712  call    ?FwTelemetryEventWriteError@@YAXQEADI@Z; FwTelemetryEventWriteError(char * const,uint)
0x18000e717  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e71e  jmp     loc_18000E4F3
0x18000e723  mov     rcx, [rcx+10h]
0x18000e727  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000e72e  mov     edx, 273h
0x18000e733  mov     r9d, edi
0x18000e736  call    WPP_SF_d
0x18000e73b  jmp     loc_18000E507
```
