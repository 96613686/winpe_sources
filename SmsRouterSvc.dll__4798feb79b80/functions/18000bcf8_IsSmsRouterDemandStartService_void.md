# IsSmsRouterDemandStartService(void)

- ea: `0x18000bcf8`
- end: `0x18000bec4`
- name: `?IsSmsRouterDemandStartService@@YAHXZ`
- size: `460`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000c430`

## callees

- `0x180003a60`
- `0x180003f50`
- `0x180003f8c`
- `0x18000bcf8`
- `0x180051420`
- `0x180051628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be5c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000bd8d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000bd8d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000be8c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000be95`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000be8c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000be95`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000bd3f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000bd3f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000bde2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000be0f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000bde2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000be0f`

## string_xrefs

- `0x18000bd5f`: `OpenSCManager for SmsRouter Service failed`
- `0x18000bd6e`: `IsSmsRouterDemandStartService`
- `0x18000bdbc`: `IsSmsRouterDemandStartService`
- `0x18000be2b`: `IsSmsRouterDemandStartService`
- `0x18000be7d`: `IsSmsRouterDemandStartService`
- `0x18000bdad`: `OpenService for SmsRouter Service failed`
- `0x18000be1f`: `SmsRouter Service start type is %d`
- `0x18000be73`: `QueryServiceConfig for SmsRouter Service failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 IsSmsRouterDemandStartService(void)
{
  BOOL v0; // r14d
  struct _QUERY_SERVICE_CONFIGW *v1; // rbx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  signed int v4; // eax
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  signed int LastError; // eax
  DWORD dwStartType; // edi
  signed int v9; // eax
  unsigned int v10; // edx
  __int64 pcbBytesNeeded; // [rsp+20h] [rbp-58h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v13; // [rsp+28h] [rbp-50h]
  _BYTE ServiceName[24]; // [rsp+30h] [rbp-48h] BYREF

  v0 = 0;
  LODWORD(pcbBytesNeeded) = 0;
  wcscpy((wchar_t *)ServiceName, L"smsrouter");
  v1 = 0;
  v13 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, (LPCWSTR)ServiceName, 0x15u);
    v6 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LogSmsRouterError(
        "IsSmsRouterDemandStartService",
        0x7Au,
        LastError,
        "OpenService for SmsRouter Service failed",
        pcbBytesNeeded,
        v13,
        *(_QWORD *)ServiceName,
        *(_QWORD *)&ServiceName[8],
        *(_QWORD *)&ServiceName[16]);
      goto LABEL_20;
    }
    LODWORD(pcbBytesNeeded) = 0;
    QueryServiceConfigW(v5, 0, 0, (LPDWORD)&pcbBytesNeeded);
    if ( (_DWORD)pcbBytesNeeded )
    {
      v1 = (struct _QUERY_SERVICE_CONFIGW *)operator new[]((unsigned int)pcbBytesNeeded);
      v13 = v1;
      if ( QueryServiceConfigW(v6, v1, pcbBytesNeeded, (LPDWORD)&pcbBytesNeeded) )
      {
        dwStartType = v1->dwStartType;
        LogSmsRouterInfo("IsSmsRouterDemandStartService", 0x87u, "SmsRouter Service start type is %d", dwStartType);
        v0 = dwStartType == 3;
LABEL_19:
        CloseServiceHandle(v6);
LABEL_20:
        CloseServiceHandle(v3);
        goto LABEL_21;
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = 140;
    }
    else
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = 147;
    }
    LogSmsRouterError("IsSmsRouterDemandStartService", v10, v9, "QueryServiceConfig for SmsRouter Service failed");
    goto LABEL_19;
  }
  v4 = GetLastError();
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  LogSmsRouterError(
    "IsSmsRouterDemandStartService",
    0x72u,
    v4,
    "OpenSCManager for SmsRouter Service failed",
    pcbBytesNeeded,
    v13,
    *(_QWORD *)ServiceName,
    *(_QWORD *)&ServiceName[8],
    *(_QWORD *)&ServiceName[16]);
LABEL_21:
  if ( v1 )
    operator delete(v1);
  return v0;
}

```

## disassembly

```asm
0x18000bcf8  push    rbx
0x18000bcfa  push    rbp
0x18000bcfb  push    rsi
0x18000bcfc  push    rdi
0x18000bcfd  push    r14
0x18000bcff  sub     rsp, 50h
0x18000bd03  mov     rax, cs:__security_cookie
0x18000bd0a  xor     rax, rsp
0x18000bd0d  mov     [rsp+78h+var_30], rax
0x18000bd12  xor     r14d, r14d
0x18000bd15  mov     dword ptr [rsp+78h+pcbBytesNeeded], r14d
0x18000bd1a  movups  xmm0, xmmword ptr cs:aSmsrouter_0; "smsrouter"
0x18000bd21  movups  xmmword ptr [rsp+78h+ServiceName], xmm0
0x18000bd26  mov     eax, dword ptr cs:aSmsrouter_0+10h; "r"
0x18000bd2c  mov     [rsp+78h+var_38], eax
0x18000bd30  xor     ebx, ebx
0x18000bd32  mov     [rsp+78h+var_50], rbx
0x18000bd37  xor     edx, edx; lpDatabaseName
0x18000bd39  xor     ecx, ecx; lpMachineName
0x18000bd3b  lea     r8d, [r14+1]; dwDesiredAccess
0x18000bd3f  call    cs:__imp_OpenSCManagerW
0x18000bd45  mov     rbp, rax
0x18000bd48  test    rax, rax
0x18000bd4b  jnz     short loc_18000BD7F
0x18000bd4d  call    cs:__imp_GetLastError
0x18000bd53  test    eax, eax
0x18000bd55  jle     short loc_18000BD5F
0x18000bd57  movzx   eax, ax
0x18000bd5a  or      eax, 80070000h
0x18000bd5f  lea     r9, aOpenscmanagerF; "OpenSCManager for SmsRouter Service fai"...
0x18000bd66  mov     r8d, eax; int
0x18000bd69  mov     edx, 72h ; 'r'; unsigned int
0x18000bd6e  lea     rcx, aIssmsrouterdem; "IsSmsRouterDemandStartService"
0x18000bd75  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000bd7a  jmp     loc_18000BE9C
0x18000bd7f  mov     r8d, 15h; dwDesiredAccess
0x18000bd85  lea     rdx, [rsp+78h+ServiceName]; lpServiceName
0x18000bd8a  mov     rcx, rbp; hSCManager
0x18000bd8d  call    cs:__imp_OpenServiceW
0x18000bd93  mov     rsi, rax
0x18000bd96  test    rax, rax
0x18000bd99  jnz     short loc_18000BDCD
0x18000bd9b  call    cs:__imp_GetLastError
0x18000bda1  test    eax, eax
0x18000bda3  jle     short loc_18000BDAD
0x18000bda5  movzx   eax, ax
0x18000bda8  or      eax, 80070000h
0x18000bdad  lea     r9, aOpenserviceFor_0; "OpenService for SmsRouter Service faile"...
0x18000bdb4  mov     r8d, eax; int
0x18000bdb7  mov     edx, 7Ah ; 'z'; unsigned int
0x18000bdbc  lea     rcx, aIssmsrouterdem; "IsSmsRouterDemandStartService"
0x18000bdc3  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000bdc8  jmp     loc_18000BE92
0x18000bdcd  mov     dword ptr [rsp+78h+pcbBytesNeeded], 0
0x18000bdd5  lea     r9, [rsp+78h+pcbBytesNeeded]; pcbBytesNeeded
0x18000bdda  xor     r8d, r8d; cbBufSize
0x18000bddd  xor     edx, edx; lpServiceConfig
0x18000bddf  mov     rcx, rsi; hService
0x18000bde2  call    cs:__imp_QueryServiceConfigW
0x18000bde8  mov     eax, dword ptr [rsp+78h+pcbBytesNeeded]
0x18000bdec  test    eax, eax
0x18000bdee  jz      short loc_18000BE5C
0x18000bdf0  mov     ecx, eax; unsigned __int64
0x18000bdf2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bdf7  mov     rbx, rax
0x18000bdfa  mov     [rsp+78h+var_50], rax
0x18000bdff  lea     r9, [rsp+78h+pcbBytesNeeded]; pcbBytesNeeded
0x18000be04  mov     r8d, dword ptr [rsp+78h+pcbBytesNeeded]; cbBufSize
0x18000be09  mov     rdx, rax; lpServiceConfig
0x18000be0c  mov     rcx, rsi; hService
0x18000be0f  call    cs:__imp_QueryServiceConfigW
0x18000be15  test    eax, eax
0x18000be17  jz      short loc_18000BE43
0x18000be19  mov     edi, [rbx+4]
0x18000be1c  mov     r9d, edi
0x18000be1f  lea     r8, aSmsrouterServi; "SmsRouter Service start type is %d"
0x18000be26  mov     edx, 87h; unsigned int
0x18000be2b  lea     rcx, aIssmsrouterdem; "IsSmsRouterDemandStartService"
0x18000be32  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000be37  xor     r14d, r14d
0x18000be3a  cmp     edi, 3
0x18000be3d  setz    r14b
0x18000be41  jmp     short loc_18000BE89
0x18000be43  call    cs:__imp_GetLastError
0x18000be49  test    eax, eax
0x18000be4b  jle     short loc_18000BE55
0x18000be4d  movzx   eax, ax
0x18000be50  or      eax, 80070000h
0x18000be55  mov     edx, 8Ch
0x18000be5a  jmp     short loc_18000BE73
0x18000be5c  call    cs:__imp_GetLastError
0x18000be62  test    eax, eax
0x18000be64  jle     short loc_18000BE6E
0x18000be66  movzx   eax, ax
0x18000be69  or      eax, 80070000h
0x18000be6e  mov     edx, 93h; unsigned int
0x18000be73  lea     r9, aQueryserviceco_0; "QueryServiceConfig for SmsRouter Servic"...
0x18000be7a  mov     r8d, eax; int
0x18000be7d  lea     rcx, aIssmsrouterdem; "IsSmsRouterDemandStartService"
0x18000be84  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000be89  mov     rcx, rsi; hSCObject
0x18000be8c  call    cs:__imp_CloseServiceHandle
0x18000be92  mov     rcx, rbp; hSCObject
0x18000be95  call    cs:__imp_CloseServiceHandle
0x18000be9b  nop
0x18000be9c  test    rbx, rbx
0x18000be9f  jz      short loc_18000BEA9
0x18000bea1  mov     rcx, rbx; Block
0x18000bea4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bea9  mov     eax, r14d
0x18000beac  mov     rcx, [rsp+78h+var_30]
0x18000beb1  xor     rcx, rsp; StackCookie
0x18000beb4  call    __security_check_cookie
0x18000beb9  add     rsp, 50h
0x18000bebd  pop     r14
0x18000bebf  pop     rdi
0x18000bec0  pop     rsi
0x18000bec1  pop     rbp
0x18000bec2  pop     rbx
0x18000bec3  retn
```
