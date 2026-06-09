# BfeFwTriggerInit

- ea: `0x180041ca0`
- end: `0x180041eda`
- name: `BfeFwTriggerInit`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18003e190`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180041ca0`
- `0x180041ee0`
- `0x180058b30`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180041ece`
- `ntdll!EtwEventUnregister` at `0x180041ece`
- `ntdll!EtwEventRegister` at `0x180041ce5`
- `ntdll!EtwEventRegister` at `0x180041ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e09`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041cfb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041cfb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041e7d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041e7d`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180041d9e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180041df6`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180041d9e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180041df6`

## string_xrefs

- `0x180041d0f`: `OpenSCManagerW`
- `0x180041e9c`: `EnumServicesStatusExW`

## pseudocode

```c
__int64 BfeFwTriggerInit()
{
  LPBYTE v0; // rdi
  DWORD LastError; // eax
  __int64 v2; // rcx
  SC_HANDLE v3; // r14
  const char *v4; // rdx
  __int64 v5; // rbx
  unsigned int i; // esi
  DWORD v8; // edi
  DWORD v9; // r15d
  __int64 v10; // rcx
  DWORD v11; // esi
  DWORD cbBufSize; // [rsp+28h] [rbp-50h]
  LPBYTE lpServices; // [rsp+50h] [rbp-28h] BYREF
  DWORD pcbBytesNeeded; // [rsp+58h] [rbp-20h] BYREF
  DWORD ServicesReturned; // [rsp+5Ch] [rbp-1Ch] BYREF

  v0 = 0;
  pcbBytesNeeded = 0;
  lpServices = 0;
  ServicesReturned = 0;
  LastError = EtwEventRegister(Symbol_BfeTriggerProvider, 0, 0, MEMORY[0x1800EF080]);
  if ( LastError )
  {
    v4 = "EtwEventRegister";
    goto LABEL_4;
  }
  v3 = OpenSCManagerW(0, 0, 5u);
  if ( !v3 )
  {
    LastError = GetLastError();
    v4 = "OpenSCManagerW";
LABEL_4:
    v5 = WfpReportSysErrorAsWinError(v2, v4, LastError);
    goto LABEL_5;
  }
  v5 = 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( i >= 3 )
    {
      v8 = 0x40000;
      pcbBytesNeeded = 0x40000;
    }
    else
    {
      EnumServicesStatusExW(v3, SC_ENUM_PROCESS_INFO, 0x30u, 3u, 0, 0, &pcbBytesNeeded, &ServicesReturned, 0, 0);
      v8 = pcbBytesNeeded;
    }
    v5 = WfpMemAlloc(v8, 0);
    if ( v5 )
    {
      v0 = lpServices;
      goto LABEL_20;
    }
    cbBufSize = v8;
    v0 = lpServices;
    if ( EnumServicesStatusExW(
           v3,
           SC_ENUM_PROCESS_INFO,
           0x30u,
           3u,
           lpServices,
           cbBufSize,
           &pcbBytesNeeded,
           &ServicesReturned,
           0,
           0) )
    {
      break;
    }
    v9 = GetLastError();
    if ( GetLastError() == 234 )
    {
      WfpMemFree(&lpServices);
      v0 = 0;
      lpServices = 0;
    }
    else if ( v9 )
    {
      v5 = WfpReportSysErrorAsWinError(v10, "EnumServicesStatusExW", v9);
      goto LABEL_20;
    }
  }
  v11 = 0;
  qword_1800F2668[328] = (__int64)&qword_1800F2668[327];
  for ( qword_1800F2668[327] = (__int64)&qword_1800F2668[327]; v11 < ServicesReturned; ++v11 )
  {
    v5 = BfeFwTriggerBuildDb(v3, (const WCHAR **)&v0[56 * v11]);
    if ( v5 )
      break;
  }
LABEL_20:
  if ( v0 )
    WfpMemFree(&lpServices);
  CloseServiceHandle(v3);
LABEL_5:
  if ( v5 )
  {
    if ( MEMORY[0x1800EF080][0] )
      EtwEventUnregister();
    WfpReportError(v5, "BfeFwTriggerInit");
  }
  return v5;
}

```

## disassembly

```asm
0x180041ca0  push    rbp
0x180041ca2  push    rbx
0x180041ca3  push    rsi
0x180041ca4  push    rdi
0x180041ca5  push    r14
0x180041ca7  push    r15
0x180041ca9  mov     rbp, rsp
0x180041cac  sub     rsp, 78h
0x180041cb0  mov     rax, cs:__security_cookie
0x180041cb7  xor     rax, rsp
0x180041cba  mov     [rbp+var_18], rax
0x180041cbe  xor     edi, edi
0x180041cc0  mov     [rbp+var_20], 0
0x180041cc7  lea     r9, cs:1800EF080h
0x180041cce  mov     [rbp+var_28], rdi
0x180041cd2  xor     r8d, r8d
0x180041cd5  mov     [rbp+ServicesReturned], 0
0x180041cdc  xor     edx, edx
0x180041cde  lea     rcx, Symbol_BfeTriggerProvider
0x180041ce5  call    cs:__imp_EtwEventRegister
0x180041ceb  test    eax, eax
0x180041ced  jnz     loc_180041E88
0x180041cf3  xor     edx, edx; lpDatabaseName
0x180041cf5  lea     r8d, [rdi+5]; dwDesiredAccess
0x180041cf9  xor     ecx, ecx; lpMachineName
0x180041cfb  call    cs:__imp_OpenSCManagerW
0x180041d01  mov     r14, rax
0x180041d04  test    rax, rax
0x180041d07  jnz     short loc_180041D46
0x180041d09  call    cs:__imp_GetLastError
0x180041d0f  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW"
0x180041d16  mov     r8d, eax
0x180041d19  call    WfpReportSysErrorAsWinError
0x180041d1e  mov     rbx, rax
0x180041d21  test    rbx, rbx
0x180041d24  jnz     loc_180041EBE
0x180041d2a  mov     rax, rbx
0x180041d2d  mov     rcx, [rbp+var_18]
0x180041d31  xor     rcx, rsp; StackCookie
0x180041d34  call    __security_check_cookie
0x180041d39  add     rsp, 78h
0x180041d3d  pop     r15
0x180041d3f  pop     r14
0x180041d41  pop     rdi
0x180041d42  pop     rsi
0x180041d43  pop     rbx
0x180041d44  pop     rbp
0x180041d45  retn
0x180041d46  xor     ebx, ebx
0x180041d48  xor     esi, esi
0x180041d4a  cmp     esi, 4
0x180041d4d  jnb     loc_180041E39
0x180041d53  cmp     esi, 3
0x180041d56  jnb     loc_180041E2C
0x180041d5c  mov     [rsp+78h+pszGroupName], 0; pszGroupName
0x180041d65  lea     rax, [rbp+ServicesReturned]
0x180041d69  mov     [rsp+78h+lpResumeHandle], 0; lpResumeHandle
0x180041d72  xor     edx, edx; InfoLevel
0x180041d74  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180041d79  mov     rcx, r14; hSCManager
0x180041d7c  lea     rax, [rbp+var_20]
0x180041d80  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180041d85  mov     [rsp+78h+cbBufSize], 0; cbBufSize
0x180041d8d  lea     r9d, [rdx+3]; dwServiceState
0x180041d91  lea     r8d, [rdx+30h]; dwServiceType
0x180041d95  mov     [rsp+78h+lpServices], 0; lpServices
0x180041d9e  call    cs:__imp_EnumServicesStatusExW
0x180041da4  mov     edi, [rbp+var_20]
0x180041da7  mov     ecx, edi; dwBytes
0x180041da9  lea     r8, [rbp+var_28]
0x180041dad  xor     edx, edx; dwFlags
0x180041daf  call    WfpMemAlloc
0x180041db4  mov     rbx, rax
0x180041db7  test    rax, rax
0x180041dba  jnz     loc_180041EAD
0x180041dc0  mov     [rsp+78h+pszGroupName], rax; pszGroupName
0x180041dc5  lea     r9d, [rbx+3]; dwServiceState
0x180041dc9  mov     [rsp+78h+lpResumeHandle], rax; lpResumeHandle
0x180041dce  lea     r8d, [rbx+30h]; dwServiceType
0x180041dd2  lea     rax, [rbp+ServicesReturned]
0x180041dd6  xor     edx, edx; InfoLevel
0x180041dd8  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180041ddd  mov     rcx, r14; hSCManager
0x180041de0  lea     rax, [rbp+var_20]
0x180041de4  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180041de9  mov     [rsp+78h+cbBufSize], edi; cbBufSize
0x180041ded  mov     rdi, [rbp+var_28]
0x180041df1  mov     [rsp+78h+lpServices], rdi; lpServices
0x180041df6  call    cs:__imp_EnumServicesStatusExW
0x180041dfc  test    eax, eax
0x180041dfe  jnz     short loc_180041E39
0x180041e00  call    cs:__imp_GetLastError
0x180041e06  mov     r15d, eax
0x180041e09  call    cs:__imp_GetLastError
0x180041e0f  cmp     eax, 0EAh
0x180041e14  jnz     short loc_180041E94
0x180041e16  lea     rcx, [rbp+var_28]
0x180041e1a  call    WfpMemFree
0x180041e1f  xor     edi, edi
0x180041e21  mov     [rbp+var_28], rdi
0x180041e25  inc     esi
0x180041e27  jmp     loc_180041D4A
0x180041e2c  mov     edi, 40000h
0x180041e31  mov     [rbp+var_20], edi
0x180041e34  jmp     loc_180041DA7
0x180041e39  lea     rax, qword_1800F2668+0A38h
0x180041e40  xor     esi, esi
0x180041e42  mov     cs:qword_1800F2668+0A40h, rax
0x180041e49  mov     cs:qword_1800F2668+0A38h, rax
0x180041e50  cmp     [rbp+ServicesReturned], esi
0x180041e53  jbe     short loc_180041E75
0x180041e55  mov     eax, esi
0x180041e57  mov     rcx, r14
0x180041e5a  imul    rdx, rax, 38h ; '8'
0x180041e5e  add     rdx, rdi
0x180041e61  call    BfeFwTriggerBuildDb
0x180041e66  mov     rbx, rax
0x180041e69  test    rax, rax
0x180041e6c  jnz     short loc_180041E75
0x180041e6e  inc     esi
0x180041e70  cmp     esi, [rbp+ServicesReturned]
0x180041e73  jb      short loc_180041E55
0x180041e75  test    rdi, rdi
0x180041e78  jnz     short loc_180041EB3
0x180041e7a  mov     rcx, r14; hSCObject
0x180041e7d  call    cs:__imp_CloseServiceHandle
0x180041e83  jmp     loc_180041D21
0x180041e88  lea     rdx, aEtweventregist; "EtwEventRegister"
0x180041e8f  jmp     loc_180041D16
0x180041e94  test    r15d, r15d
0x180041e97  jz      short loc_180041E25
0x180041e99  mov     r8d, r15d
0x180041e9c  lea     rdx, aEnumservicesst_0; "EnumServicesStatusExW"
0x180041ea3  call    WfpReportSysErrorAsWinError
0x180041ea8  mov     rbx, rax
0x180041eab  jmp     short loc_180041E75
0x180041ead  mov     rdi, [rbp+var_28]
0x180041eb1  jmp     short loc_180041E75
0x180041eb3  lea     rcx, [rbp+var_28]
0x180041eb7  call    WfpMemFree
0x180041ebc  jmp     short loc_180041E7A
0x180041ebe  mov     rcx, cs:1800EF080h
0x180041ec5  test    rcx, rcx
0x180041ec8  jz      loc_18008A782
0x180041ece  call    cs:__imp_EtwEventUnregister
0x180041ed4  nop
0x180041ed5  jmp     loc_18008A782
0x18008a782  lea     rdx, aBfefwtriggerin; "BfeFwTriggerInit"
0x18008a789  mov     rcx, rbx
0x18008a78c  call    WfpReportError
0x18008a791  nop
0x18008a792  jmp     loc_180041D2A
```
