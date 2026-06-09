# BfeTxnLockInit

- ea: `0x180056f84`
- end: `0x1800570fb`
- name: `BfeTxnLockInit`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800403d0`

## callees

- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180031694`
- `0x18004ab24`
- `0x180056f84`
- `0x1800572ec`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180056fff`
- `ntdll!TpAllocTimer` at `0x180056fff`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180056fbb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180056fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056fd3`

## string_xrefs

- `0x180057037`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180057089`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180056fdf`: `CreateSemaphoreW`

## pseudocode

```c
__int64 BfeTxnLockInit()
{
  DWORD LastError; // eax
  __int64 v1; // rcx
  const char *v2; // rdx
  int v3; // eax
  __int64 v4; // rcx
  int v5; // r9d
  __int64 v6; // rax
  __int64 DWord; // rbx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // r9d
  int v12; // eax
  int v14; // [rsp+40h] [rbp+10h] BYREF
  int v15; // [rsp+48h] [rbp+18h] BYREF

  v15 = 0;
  v14 = 0;
  gBfeTxnComponent = CreateSemaphoreExW(0, 1, 1, 0, 0, 0x1F0003u);
  if ( !gBfeTxnComponent )
  {
    LastError = GetLastError();
    v2 = "CreateSemaphoreW";
LABEL_14:
    v6 = WfpReportSysErrorAsWinError(v1, v2, LastError);
LABEL_15:
    DWord = v6;
    if ( v6 )
      goto LABEL_16;
    return DWord;
  }
  v3 = TpAllocTimer(&qword_1800F5CD8, BfeTxnLockOnTimeout, 0, 0);
  if ( v3 < 0 )
  {
    v6 = WfpReportSysErrorAsNtStatus(v4, "TpAllocTimer", (unsigned int)v3);
    goto LABEL_15;
  }
  DWord = BfeRegQueryDWord(
            v4,
            (unsigned int)L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
            (unsigned int)L"TxnWatchdogTimeoutInMSec",
            v5,
            (__int64)&v15,
            (__int64)&v14);
  if ( DWord )
  {
LABEL_16:
    WfpReportError(DWord, "BfeTxnLockInit");
    return DWord;
  }
  v8 = 500;
  if ( v14 )
    v8 = v15;
  dword_1800F5CE4 = v8;
  if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() )
  {
    v14 = 0;
    v15 = 0;
    BfeRegQueryDWord(
      v10,
      (unsigned int)L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
      (unsigned int)L"KernelWatchdogTimeoutOverrideInMSec",
      v11,
      (__int64)&v15,
      (__int64)&v14);
    v12 = 3600000;
    if ( v14 )
      v12 = v15;
    dword_1800F5CFC = v12;
  }
  LastError = McGenEventRegister_EtwEventRegister(
                &MICROSOFT_WFP_PROVIDER,
                v9,
                &MICROSOFT_WFP_PROVIDER_Context,
                &MICROSOFT_WFP_PROVIDER_Context);
  if ( LastError )
  {
    v2 = "EventRegisterMicrosoft_Windows_WFP";
    goto LABEL_14;
  }
  return DWord;
}

```

## disassembly

```asm
0x180056f84  mov     [rsp-8+arg_10], rbx
0x180056f89  push    rbp
0x180056f8a  mov     rbp, rsp
0x180056f8d  sub     rsp, 30h
0x180056f91  xor     r9d, r9d; lpName
0x180056f94  mov     [rsp+30h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180056f9c  xor     ecx, ecx; lpSemaphoreAttributes
0x180056f9e  mov     [rbp+arg_8], 0
0x180056fa5  mov     [rbp+arg_0], 0
0x180056fac  mov     [rsp+30h+dwFlags], 0; dwFlags
0x180056fb4  lea     edx, [r9+1]; lInitialCount
0x180056fb8  mov     r8d, edx; lMaximumCount
0x180056fbb  call    cs:__imp_CreateSemaphoreExW
0x180056fc2  nop     dword ptr [rax+rax+00h]
0x180056fc7  mov     cs:gBfeTxnComponent, rax
0x180056fce  test    rax, rax
0x180056fd1  jnz     short loc_180056FEB
0x180056fd3  call    cs:__imp_GetLastError
0x180056fda  nop     dword ptr [rax+rax+00h]
0x180056fdf  lea     rdx, aCreatesemaphor; "CreateSemaphoreW"
0x180056fe6  jmp     loc_1800570CD
0x180056feb  xor     r9d, r9d
0x180056fee  lea     rdx, BfeTxnLockOnTimeout
0x180056ff5  xor     r8d, r8d
0x180056ff8  lea     rcx, qword_1800F5CD8
0x180056fff  call    cs:__imp_TpAllocTimer
0x180057006  nop     dword ptr [rax+rax+00h]
0x18005700b  test    eax, eax
0x18005700d  jns     short loc_180057023
0x18005700f  mov     r8d, eax
0x180057012  lea     rdx, aTpalloctimer; "TpAllocTimer"
0x180057019  call    WfpReportSysErrorAsNtStatus
0x18005701e  jmp     loc_1800570D5
0x180057023  lea     rax, [rbp+arg_0]
0x180057027  mov     qword ptr [rsp+30h+dwDesiredAccess], rax
0x18005702c  lea     r8, aTxnwatchdogtim; "TxnWatchdogTimeoutInMSec"
0x180057033  lea     rax, [rbp+arg_8]
0x180057037  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\BF"...
0x18005703e  mov     qword ptr [rsp+30h+dwFlags], rax
0x180057043  call    BfeRegQueryDWord
0x180057048  mov     rbx, rax
0x18005704b  test    rax, rax
0x18005704e  jnz     loc_1800570DD
0x180057054  cmp     [rbp+arg_0], ebx
0x180057057  mov     eax, 1F4h
0x18005705c  cmovnz  eax, [rbp+arg_8]
0x180057060  mov     cs:dword_1800F5CE4, eax
0x180057066  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18005706b  test    eax, eax
0x18005706d  jz      short loc_1800570AC
0x18005706f  lea     rax, [rbp+arg_0]
0x180057073  mov     [rbp+arg_0], ebx
0x180057076  mov     qword ptr [rsp+30h+dwDesiredAccess], rax
0x18005707b  lea     r8, aKernelwatchdog; "KernelWatchdogTimeoutOverrideInMSec"
0x180057082  lea     rax, [rbp+arg_8]
0x180057086  mov     [rbp+arg_8], ebx
0x180057089  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\BF"...
0x180057090  mov     qword ptr [rsp+30h+dwFlags], rax
0x180057095  call    BfeRegQueryDWord
0x18005709a  cmp     [rbp+arg_0], ebx
0x18005709d  mov     eax, 36EE80h
0x1800570a2  cmovnz  eax, [rbp+arg_8]
0x1800570a6  mov     cs:dword_1800F5CFC, eax
0x1800570ac  lea     r8, MICROSOFT_WFP_PROVIDER_Context
0x1800570b3  mov     r9, r8
0x1800570b6  lea     rcx, MICROSOFT_WFP_PROVIDER
0x1800570bd  call    McGenEventRegister_EtwEventRegister
0x1800570c2  test    eax, eax
0x1800570c4  jz      short loc_1800570EC
0x1800570c6  lea     rdx, aEventregisterm; "EventRegisterMicrosoft_Windows_WFP"
0x1800570cd  mov     r8d, eax
0x1800570d0  call    WfpReportSysErrorAsWinError
0x1800570d5  mov     rbx, rax
0x1800570d8  test    rax, rax
0x1800570db  jz      short loc_1800570EC
0x1800570dd  lea     rdx, aBfetxnlockinit; "BfeTxnLockInit"
0x1800570e4  mov     rcx, rbx
0x1800570e7  call    WfpReportError
0x1800570ec  mov     rax, rbx
0x1800570ef  mov     rbx, [rsp+30h+arg_10]
0x1800570f4  add     rsp, 30h
0x1800570f8  pop     rbp
0x1800570f9  retn
```
