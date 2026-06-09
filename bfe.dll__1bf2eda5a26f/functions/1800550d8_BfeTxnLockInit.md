# BfeTxnLockInit

- ea: `0x1800550d8`
- end: `0x18005523c`
- name: `BfeTxnLockInit`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f140`

## callees

- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x18002fd7c`
- `0x180048c7c`
- `0x1800550d8`
- `0x180055424`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180055147`
- `ntdll!TpAllocTimer` at `0x180055147`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18005510f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18005510f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055121`

## string_xrefs

- `0x180055179`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x1800551cb`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180055127`: `CreateSemaphoreW`

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
  qword_1800F2668[199] = (__int64)CreateSemaphoreExW(0, 1, 1, 0, 0, 0x1F0003u);
  if ( !qword_1800F2668[199] )
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
  v3 = TpAllocTimer(&qword_1800F2668[202], BfeTxnLockOnTimeout, 0, 0);
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
  HIDWORD(qword_1800F2668[203]) = v8;
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
    HIDWORD(qword_1800F2668[206]) = v12;
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
0x1800550d8  mov     [rsp-8+arg_10], rbx
0x1800550dd  push    rbp
0x1800550de  mov     rbp, rsp
0x1800550e1  sub     rsp, 30h
0x1800550e5  xor     r9d, r9d; lpName
0x1800550e8  mov     [rsp+30h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800550f0  xor     ecx, ecx; lpSemaphoreAttributes
0x1800550f2  mov     [rbp+arg_8], 0
0x1800550f9  mov     [rbp+arg_0], 0
0x180055100  mov     [rsp+30h+dwFlags], 0; dwFlags
0x180055108  lea     edx, [r9+1]; lInitialCount
0x18005510c  mov     r8d, edx; lMaximumCount
0x18005510f  call    cs:__imp_CreateSemaphoreExW
0x180055115  mov     cs:qword_1800F2668+638h, rax
0x18005511c  test    rax, rax
0x18005511f  jnz     short loc_180055133
0x180055121  call    cs:__imp_GetLastError
0x180055127  lea     rdx, aCreatesemaphor; "CreateSemaphoreW"
0x18005512e  jmp     loc_18005520F
0x180055133  xor     r9d, r9d
0x180055136  lea     rdx, BfeTxnLockOnTimeout
0x18005513d  xor     r8d, r8d
0x180055140  lea     rcx, qword_1800F2668+650h
0x180055147  call    cs:__imp_TpAllocTimer
0x18005514d  test    eax, eax
0x18005514f  jns     short loc_180055165
0x180055151  mov     r8d, eax
0x180055154  lea     rdx, aTpalloctimer; "TpAllocTimer"
0x18005515b  call    WfpReportSysErrorAsNtStatus
0x180055160  jmp     loc_180055217
0x180055165  lea     rax, [rbp+arg_0]
0x180055169  mov     qword ptr [rsp+30h+dwDesiredAccess], rax
0x18005516e  lea     r8, aTxnwatchdogtim; "TxnWatchdogTimeoutInMSec"
0x180055175  lea     rax, [rbp+arg_8]
0x180055179  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\BF"...
0x180055180  mov     qword ptr [rsp+30h+dwFlags], rax
0x180055185  call    BfeRegQueryDWord
0x18005518a  mov     rbx, rax
0x18005518d  test    rax, rax
0x180055190  jnz     loc_18005521F
0x180055196  cmp     [rbp+arg_0], ebx
0x180055199  mov     eax, 1F4h
0x18005519e  cmovnz  eax, [rbp+arg_8]
0x1800551a2  mov     dword ptr cs:qword_1800F2668+65Ch, eax
0x1800551a8  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x1800551ad  test    eax, eax
0x1800551af  jz      short loc_1800551EE
0x1800551b1  lea     rax, [rbp+arg_0]
0x1800551b5  mov     [rbp+arg_0], ebx
0x1800551b8  mov     qword ptr [rsp+30h+dwDesiredAccess], rax
0x1800551bd  lea     r8, aKernelwatchdog; "KernelWatchdogTimeoutOverrideInMSec"
0x1800551c4  lea     rax, [rbp+arg_8]
0x1800551c8  mov     [rbp+arg_8], ebx
0x1800551cb  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\BF"...
0x1800551d2  mov     qword ptr [rsp+30h+dwFlags], rax
0x1800551d7  call    BfeRegQueryDWord
0x1800551dc  cmp     [rbp+arg_0], ebx
0x1800551df  mov     eax, 36EE80h
0x1800551e4  cmovnz  eax, [rbp+arg_8]
0x1800551e8  mov     dword ptr cs:qword_1800F2668+674h, eax
0x1800551ee  lea     r8, MICROSOFT_WFP_PROVIDER_Context
0x1800551f5  mov     r9, r8
0x1800551f8  lea     rcx, MICROSOFT_WFP_PROVIDER
0x1800551ff  call    McGenEventRegister_EtwEventRegister
0x180055204  test    eax, eax
0x180055206  jz      short loc_18005522E
0x180055208  lea     rdx, aEventregisterm; "EventRegisterMicrosoft_Windows_WFP"
0x18005520f  mov     r8d, eax
0x180055212  call    WfpReportSysErrorAsWinError
0x180055217  mov     rbx, rax
0x18005521a  test    rax, rax
0x18005521d  jz      short loc_18005522E
0x18005521f  lea     rdx, aBfetxnlockinit; "BfeTxnLockInit"
0x180055226  mov     rcx, rbx
0x180055229  call    WfpReportError
0x18005522e  mov     rax, rbx
0x180055231  mov     rbx, [rsp+30h+arg_10]
0x180055236  add     rsp, 30h
0x18005523a  pop     rbp
0x18005523b  retn
```
