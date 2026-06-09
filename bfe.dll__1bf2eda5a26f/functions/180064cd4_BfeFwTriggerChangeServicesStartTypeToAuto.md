# BfeFwTriggerChangeServicesStartTypeToAuto

- ea: `0x180064cd4`
- end: `0x180064df7`
- name: `BfeFwTriggerChangeServicesStartTypeToAuto`
- size: `291`
- prototype: `int __fastcall(SC_HANDLE hSCManager)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180064fd0`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180022730`
- `0x180058b30`
- `0x180064b50`
- `0x180064cd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d9e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180064d43`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180064d94`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180064d43`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180064d94`

## string_xrefs

- `0x180064da7`: `EnumServicesStatusExW`

## pseudocode

```c
int __fastcall BfeFwTriggerChangeServicesStartTypeToAuto(SC_HANDLE hSCManager)
{
  DWORD cbBufSize; // ebx
  __int64 v3; // rax
  DWORD LastError; // eax
  __int64 v5; // rcx
  DWORD i; // ebx
  LPBYTE lpServices; // [rsp+50h] [rbp-28h]
  DWORD ServicesReturned; // [rsp+58h] [rbp-20h] BYREF
  DWORD pcbBytesNeeded; // [rsp+5Ch] [rbp-1Ch] BYREF

  pcbBytesNeeded = 0;
  ServicesReturned = 0;
  lpServices = 0;
  EnumServicesStatusExW(hSCManager, SC_ENUM_PROCESS_INFO, 0x30u, 3u, 0, 0, &pcbBytesNeeded, &ServicesReturned, 0, 0);
  cbBufSize = pcbBytesNeeded;
  v3 = WfpMemAlloc(pcbBytesNeeded, 0);
  if ( !v3 )
  {
    LODWORD(v3) = EnumServicesStatusExW(
                    hSCManager,
                    SC_ENUM_PROCESS_INFO,
                    0x30u,
                    3u,
                    lpServices,
                    cbBufSize,
                    &pcbBytesNeeded,
                    &ServicesReturned,
                    0,
                    0);
    if ( (_DWORD)v3 )
    {
      for ( i = 0; i < ServicesReturned; ++i )
        LODWORD(v3) = BfeFwTriggerChangeServiceStartTypeToAuto(hSCManager, 56LL * i);
    }
    else
    {
      LastError = GetLastError();
      LODWORD(v3) = WfpReportSysErrorAsWinError(v5, "EnumServicesStatusExW", LastError);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180064cd4  mov     r11, rsp
0x180064cd7  push    rbp
0x180064cd8  push    rbx
0x180064cd9  push    rsi
0x180064cda  push    rdi
0x180064cdb  mov     rbp, rsp
0x180064cde  sub     rsp, 78h
0x180064ce2  mov     rax, cs:__security_cookie
0x180064ce9  xor     rax, rsp
0x180064cec  mov     [rbp+var_18], rax
0x180064cf0  mov     qword ptr [r11-50h], 0
0x180064cf8  lea     rax, [rbp+ServicesReturned]
0x180064cfc  mov     qword ptr [r11-58h], 0
0x180064d04  xor     edx, edx; InfoLevel
0x180064d06  mov     [r11-60h], rax
0x180064d0a  mov     rsi, rcx
0x180064d0d  lea     rax, [rbp+var_1C]
0x180064d11  mov     [rbp+var_1C], 0
0x180064d18  mov     [r11-68h], rax
0x180064d1c  mov     [rsp+78h+cbBufSize], 0; cbBufSize
0x180064d24  lea     r9d, [rdx+3]; dwServiceState
0x180064d28  lea     r8d, [rdx+30h]; dwServiceType
0x180064d2c  mov     qword ptr [r11-78h], 0
0x180064d34  mov     [rbp+ServicesReturned], 0
0x180064d3b  mov     [rbp+var_28], 0
0x180064d43  call    cs:__imp_EnumServicesStatusExW
0x180064d49  mov     ebx, [rbp+var_1C]
0x180064d4c  lea     r8, [rbp+var_28]
0x180064d50  mov     ecx, ebx; dwBytes
0x180064d52  xor     edx, edx; dwFlags
0x180064d54  call    WfpMemAlloc
0x180064d59  mov     rdi, [rbp+var_28]
0x180064d5d  test    rax, rax
0x180064d60  jnz     short loc_180064DD4
0x180064d62  mov     [rsp+78h+pszGroupName], rax; pszGroupName
0x180064d67  xor     edx, edx; InfoLevel
0x180064d69  mov     [rsp+78h+lpResumeHandle], rax; lpResumeHandle
0x180064d6e  mov     rcx, rsi; hSCManager
0x180064d71  lea     rax, [rbp+ServicesReturned]
0x180064d75  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x180064d7a  lea     rax, [rbp+var_1C]
0x180064d7e  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180064d83  lea     r9d, [rdx+3]; dwServiceState
0x180064d87  mov     [rsp+78h+cbBufSize], ebx; cbBufSize
0x180064d8b  lea     r8d, [rdx+30h]; dwServiceType
0x180064d8f  mov     [rsp+78h+lpServices], rdi; lpServices
0x180064d94  call    cs:__imp_EnumServicesStatusExW
0x180064d9a  test    eax, eax
0x180064d9c  jnz     short loc_180064DB5
0x180064d9e  call    cs:__imp_GetLastError
0x180064da4  mov     r8d, eax
0x180064da7  lea     rdx, aEnumservicesst_0; "EnumServicesStatusExW"
0x180064dae  call    WfpReportSysErrorAsWinError
0x180064db3  jmp     short loc_180064DD4
0x180064db5  xor     ebx, ebx
0x180064db7  cmp     [rbp+ServicesReturned], ebx
0x180064dba  jbe     short loc_180064DD4
0x180064dbc  mov     eax, ebx
0x180064dbe  mov     rcx, rsi
0x180064dc1  imul    rdx, rax, 38h ; '8'
0x180064dc5  add     rdx, rdi
0x180064dc8  call    BfeFwTriggerChangeServiceStartTypeToAuto
0x180064dcd  inc     ebx
0x180064dcf  cmp     ebx, [rbp+ServicesReturned]
0x180064dd2  jb      short loc_180064DBC
0x180064dd4  test    rdi, rdi
0x180064dd7  jz      short loc_180064DE2
0x180064dd9  lea     rcx, [rbp+var_28]
0x180064ddd  call    WfpMemFree
0x180064de2  mov     rcx, [rbp+var_18]
0x180064de6  xor     rcx, rsp; StackCookie
0x180064de9  call    __security_check_cookie
0x180064dee  add     rsp, 78h
0x180064df2  pop     rdi
0x180064df3  pop     rsi
0x180064df4  pop     rbx
0x180064df5  pop     rbp
0x180064df6  retn
```
