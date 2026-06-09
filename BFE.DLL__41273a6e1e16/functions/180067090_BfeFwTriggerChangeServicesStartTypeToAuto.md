# BfeFwTriggerChangeServicesStartTypeToAuto

- ea: `0x180067090`
- end: `0x1800671c6`
- name: `BfeFwTriggerChangeServicesStartTypeToAuto`
- size: `310`
- prototype: `__int64 __fastcall(SC_HANDLE hSCManager)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800673d0`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x180024e40`
- `0x18005aa60`
- `0x180066ee4`
- `0x180067090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067166`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800670ff`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180067156`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800670ff`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180067156`

## string_xrefs

- `0x180067175`: `EnumServicesStatusExW`

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
        LODWORD(v3) = BfeFwTriggerChangeServiceStartTypeToAuto(hSCManager, (const WCHAR **)(56LL * i));
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
0x180067090  mov     r11, rsp
0x180067093  push    rbp
0x180067094  push    rbx
0x180067095  push    rsi
0x180067096  push    rdi
0x180067097  mov     rbp, rsp
0x18006709a  sub     rsp, 78h
0x18006709e  mov     rax, cs:__security_cookie
0x1800670a5  xor     rax, rsp
0x1800670a8  mov     [rbp+var_18], rax
0x1800670ac  mov     qword ptr [r11-50h], 0
0x1800670b4  lea     rax, [rbp+ServicesReturned]
0x1800670b8  mov     qword ptr [r11-58h], 0
0x1800670c0  xor     edx, edx; InfoLevel
0x1800670c2  mov     [r11-60h], rax
0x1800670c6  mov     rsi, rcx
0x1800670c9  lea     rax, [rbp+var_1C]
0x1800670cd  mov     [rbp+var_1C], 0
0x1800670d4  mov     [r11-68h], rax
0x1800670d8  mov     [rsp+78h+cbBufSize], 0; cbBufSize
0x1800670e0  lea     r9d, [rdx+3]; dwServiceState
0x1800670e4  lea     r8d, [rdx+30h]; dwServiceType
0x1800670e8  mov     qword ptr [r11-78h], 0
0x1800670f0  mov     [rbp+ServicesReturned], 0
0x1800670f7  mov     [rbp+var_28], 0
0x1800670ff  call    cs:__imp_EnumServicesStatusExW
0x180067106  nop     dword ptr [rax+rax+00h]
0x18006710b  mov     ebx, [rbp+var_1C]
0x18006710e  lea     r8, [rbp+var_28]
0x180067112  mov     ecx, ebx; dwBytes
0x180067114  xor     edx, edx; dwFlags
0x180067116  call    WfpMemAlloc
0x18006711b  mov     rdi, [rbp+var_28]
0x18006711f  test    rax, rax
0x180067122  jnz     short loc_1800671A2
0x180067124  mov     [rsp+78h+pszGroupName], rax; pszGroupName
0x180067129  xor     edx, edx; InfoLevel
0x18006712b  mov     [rsp+78h+lpResumeHandle], rax; lpResumeHandle
0x180067130  mov     rcx, rsi; hSCManager
0x180067133  lea     rax, [rbp+ServicesReturned]
0x180067137  mov     [rsp+78h+lpServicesReturned], rax; lpServicesReturned
0x18006713c  lea     rax, [rbp+var_1C]
0x180067140  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180067145  lea     r9d, [rdx+3]; dwServiceState
0x180067149  mov     [rsp+78h+cbBufSize], ebx; cbBufSize
0x18006714d  lea     r8d, [rdx+30h]; dwServiceType
0x180067151  mov     [rsp+78h+lpServices], rdi; lpServices
0x180067156  call    cs:__imp_EnumServicesStatusExW
0x18006715d  nop     dword ptr [rax+rax+00h]
0x180067162  test    eax, eax
0x180067164  jnz     short loc_180067183
0x180067166  call    cs:__imp_GetLastError
0x18006716d  nop     dword ptr [rax+rax+00h]
0x180067172  mov     r8d, eax
0x180067175  lea     rdx, aEnumservicesst_0; "EnumServicesStatusExW"
0x18006717c  call    WfpReportSysErrorAsWinError
0x180067181  jmp     short loc_1800671A2
0x180067183  xor     ebx, ebx
0x180067185  cmp     [rbp+ServicesReturned], ebx
0x180067188  jbe     short loc_1800671A2
0x18006718a  mov     eax, ebx
0x18006718c  mov     rcx, rsi
0x18006718f  imul    rdx, rax, 38h ; '8'
0x180067193  add     rdx, rdi
0x180067196  call    BfeFwTriggerChangeServiceStartTypeToAuto
0x18006719b  inc     ebx
0x18006719d  cmp     ebx, [rbp+ServicesReturned]
0x1800671a0  jb      short loc_18006718A
0x1800671a2  test    rdi, rdi
0x1800671a5  jz      short loc_1800671B0
0x1800671a7  lea     rcx, [rbp+var_28]
0x1800671ab  call    WfpMemFree
0x1800671b0  mov     rcx, [rbp+var_18]
0x1800671b4  xor     rcx, rsp; StackCookie
0x1800671b7  call    __security_check_cookie
0x1800671bc  add     rsp, 78h
0x1800671c0  pop     rdi
0x1800671c1  pop     rsi
0x1800671c2  pop     rbx
0x1800671c3  pop     rbp
0x1800671c4  retn
```
