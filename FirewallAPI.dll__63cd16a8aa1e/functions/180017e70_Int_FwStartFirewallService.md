# Int_FwStartFirewallService

- ea: `0x180017e70`
- end: `0x18001810d`
- name: `Int_FwStartFirewallService`
- size: `669`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000c560`

## callees

- `0x180005954`
- `0x180017e70`
- `0x1800277b0`
- `0x18004861c`
- `0x1800486d0`
- `0x180055110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001809c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001809c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180017fdd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180017fdd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017f68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018021`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001802a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180017f68`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018021`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001802a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180017f38`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180017f38`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017eb5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180017eb5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180017f8a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180017f8a`

## string_xrefs

- `0x180017e92`: `ServicesActive`
- `0x18001807e`: `OpenSCManager`
- `0x180018052`: `OpenService`
- `0x1800180ca`: `QueryServiceStatus`
- `0x180018006`: `StartService`
- `0x1800180d8`: `Int_FwStartFirewallService`

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
        WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 624, v9, LastError, (__int64)"OpenService");
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
          626,
          WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
          ServiceStatus.dwCurrentState);
      if ( StartServiceW(v8, 0, 0) )
        goto LABEL_23;
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v12 = 627;
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
      v12 = 625;
      v13 = "QueryServiceStatus";
    }
    WPP_SF_Ds(*((_QWORD *)v11 + 2), v12, v10, LastError, (__int64)v13);
    goto LABEL_23;
  }
  LastError = GetLastError();
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Ds(*((_QWORD *)WPP_GLOBAL_Control + 2), 623, v4, LastError, (__int64)"OpenSCManager");
LABEL_12:
    v5 = WPP_GLOBAL_Control;
  }
  if ( (LastError & 0x80000000) != 0 )
  {
    FwTelemetryEventWriteError("Int_FwStartFirewallService", LastError);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 628, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180017e70  push    rdi
0x180017e72  sub     rsp, 60h
0x180017e76  mov     rax, cs:__security_cookie
0x180017e7d  xor     rax, rsp
0x180017e80  mov     [rsp+68h+var_18], rax
0x180017e85  xorps   xmm0, xmm0
0x180017e88  mov     [rsp+68h+arg_0], rbx
0x180017e8d  mov     [rsp+68h+arg_8], rbp
0x180017e92  lea     rdx, DatabaseName; "ServicesActive"
0x180017e99  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180017e9e  mov     ebp, 1
0x180017ea3  mov     [rsp+68h+arg_10], rsi
0x180017eab  mov     r8d, ebp; dwDesiredAccess
0x180017eae  xor     ecx, ecx; lpMachineName
0x180017eb0  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180017eb5  call    cs:__imp_OpenSCManagerW
0x180017ebb  mov     rsi, rax
0x180017ebe  test    rax, rax
0x180017ec1  jnz     short loc_180017F20
0x180017ec3  call    cs:__imp_GetLastError
0x180017ec9  mov     edi, eax
0x180017ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ed2  lea     rbx, WPP_GLOBAL_Control
0x180017ed9  cmp     rcx, rbx
0x180017edc  jnz     loc_180018070
0x180017ee2  mov     rsi, [rsp+68h+arg_10]
0x180017eea  mov     rbp, [rsp+68h+arg_8]
0x180017eef  test    edi, edi
0x180017ef1  js      loc_1800180D6
0x180017ef7  cmp     rcx, rbx
0x180017efa  mov     rbx, [rsp+68h+arg_0]
0x180017eff  jz      short loc_180017F0B
0x180017f01  test    byte ptr [rcx+1Ch], 8
0x180017f05  jnz     loc_1800180F0
0x180017f0b  mov     eax, edi
0x180017f0d  mov     rcx, [rsp+68h+var_18]
0x180017f12  xor     rcx, rsp; StackCookie
0x180017f15  call    __security_check_cookie
0x180017f1a  add     rsp, 60h
0x180017f1e  pop     rdi
0x180017f1f  retn
0x180017f20  mov     r8d, 14h; dwDesiredAccess
0x180017f26  mov     [rsp+68h+arg_18], r14
0x180017f2e  lea     rdx, ServiceName; "MpsSvc"
0x180017f35  mov     rcx, rsi; hSCManager
0x180017f38  call    cs:__imp_OpenServiceW
0x180017f3e  mov     r14, rax
0x180017f41  test    rax, rax
0x180017f44  jnz     short loc_180017F82
0x180017f46  call    cs:__imp_GetLastError
0x180017f4c  mov     edi, eax
0x180017f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f55  lea     rbx, WPP_GLOBAL_Control
0x180017f5c  cmp     rcx, rbx
0x180017f5f  jnz     loc_180018044
0x180017f65  mov     rcx, rsi; hSCObject
0x180017f68  call    cs:__imp_CloseServiceHandle
0x180017f6e  mov     r14, [rsp+68h+arg_18]
0x180017f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f7d  jmp     loc_180017EE2
0x180017f82  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180017f87  mov     rcx, r14; hService
0x180017f8a  call    cs:__imp_QueryServiceStatus
0x180017f90  test    eax, eax
0x180017f92  jz      loc_18001809C
0x180017f98  mov     r9d, [rsp+68h+ServiceStatus.dwCurrentState]
0x180017f9d  lea     rbx, WPP_GLOBAL_Control
0x180017fa4  xor     edi, edi
0x180017fa6  cmp     r9d, 4
0x180017faa  jz      short loc_18001801E
0x180017fac  xor     ebp, ebp
0x180017fae  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fb5  cmp     rcx, rbx
0x180017fb8  jz      short loc_180017FD5
0x180017fba  test    byte ptr [rcx+1Ch], 4
0x180017fbe  jz      short loc_180017FD5
0x180017fc0  mov     rcx, [rcx+10h]
0x180017fc4  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180017fcb  mov     edx, 272h
0x180017fd0  call    WPP_SF_d
0x180017fd5  xor     r8d, r8d; lpServiceArgVectors
0x180017fd8  xor     edx, edx; dwNumServiceArgs
0x180017fda  mov     rcx, r14; hService
0x180017fdd  call    cs:__imp_StartServiceW
0x180017fe3  test    eax, eax
0x180017fe5  jnz     short loc_18001801E
0x180017fe7  call    cs:__imp_GetLastError
0x180017fed  mov     edi, eax
0x180017fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ff6  cmp     rcx, rbx
0x180017ff9  jz      short loc_18001801E
0x180017ffb  test    byte ptr [rcx+1Ch], 1
0x180017fff  jz      short loc_18001801E
0x180018001  mov     edx, 273h
0x180018006  lea     rax, aStartservice; "StartService"
0x18001800d  mov     rcx, [rcx+10h]
0x180018011  mov     r9d, edi
0x180018014  mov     [rsp+68h+var_48], rax
0x180018019  call    WPP_SF_Ds
0x18001801e  mov     rcx, rsi; hSCObject
0x180018021  call    cs:__imp_CloseServiceHandle
0x180018027  mov     rcx, r14; hSCObject
0x18001802a  call    cs:__imp_CloseServiceHandle
0x180018030  test    ebp, ebp
0x180018032  jnz     loc_180017F6E
0x180018038  mov     edx, edi; unsigned int
0x18001803a  call    ?FwTelemetryEventManualStart@@YAXPEBDI@Z; FwTelemetryEventManualStart(char const *,uint)
0x18001803f  jmp     loc_180017F6E
0x180018044  test    [rcx+1Ch], bpl
0x180018048  jz      loc_180017F65
0x18001804e  mov     rcx, [rcx+10h]
0x180018052  lea     rax, aOpenservice; "OpenService"
0x180018059  mov     edx, 270h
0x18001805e  mov     [rsp+68h+var_48], rax
0x180018063  mov     r9d, edi
0x180018066  call    WPP_SF_Ds
0x18001806b  jmp     loc_180017F65
0x180018070  test    [rcx+1Ch], bpl
0x180018074  jz      loc_180017EE2
0x18001807a  mov     rcx, [rcx+10h]
0x18001807e  lea     rax, aOpenscmanager; "OpenSCManager"
0x180018085  mov     edx, 26Fh
0x18001808a  mov     [rsp+68h+var_48], rax
0x18001808f  mov     r9d, edi
0x180018092  call    WPP_SF_Ds
0x180018097  jmp     loc_180017F76
0x18001809c  call    cs:__imp_GetLastError
0x1800180a2  mov     edi, eax
0x1800180a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180ab  lea     rbx, WPP_GLOBAL_Control
0x1800180b2  cmp     rcx, rbx
0x1800180b5  jz      loc_18001801E
0x1800180bb  test    [rcx+1Ch], bpl
0x1800180bf  jz      loc_18001801E
0x1800180c5  mov     edx, 271h
0x1800180ca  lea     rax, aQueryservicest_0; "QueryServiceStatus"
0x1800180d1  jmp     loc_18001800D
0x1800180d6  mov     edx, edi; unsigned int
0x1800180d8  lea     rcx, aIntFwstartfire; "Int_FwStartFirewallService"
0x1800180df  call    ?FwTelemetryEventWriteError@@YAXQEADI@Z; FwTelemetryEventWriteError(char * const,uint)
0x1800180e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180eb  jmp     loc_180017EF7
0x1800180f0  mov     rcx, [rcx+10h]
0x1800180f4  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800180fb  mov     edx, 274h
0x180018100  mov     r9d, edi
0x180018103  call    WPP_SF_d
0x180018108  jmp     loc_180017F0B
```
