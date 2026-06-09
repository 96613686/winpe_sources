# BfeRundownInit

- ea: `0x180046624`
- end: `0x180046748`
- name: `BfeRundownInit`
- size: `292`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d1b4`

## callees

- `0x18000474c`
- `0x18001236c`
- `0x180018b74`
- `0x18002fd7c`
- `0x180046624`
- `0x180046da0`
- `0x180073794`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180046660`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800466e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180046660`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800466e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466f6`

## string_xrefs

- `0x1800466b1`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x1800466a3`: `CommitCountThreshold`

## pseudocode

```c
__int64 BfeRundownInit()
{
  __int64 DWord; // rbx
  __int64 v1; // rcx
  int v2; // r9d
  DWORD LastError; // eax
  const char *v4; // rdx
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  gBfePeriodicRundownEnabled = 0;
  DWord = WfpCriticalSectionCreate(&gBfeRundownComponent);
  if ( !DWord )
  {
    qword_1800F2740 = CreateThreadpoolWork((PTP_WORK_CALLBACK)BfeEtwCallbackThreadCallback, 0, 0);
    if ( !qword_1800F2740 )
    {
LABEL_10:
      LastError = GetLastError();
      v4 = "BfeRundownInit";
LABEL_11:
      DWord = WfpReportSysErrorAsWinError(v1, v4, LastError);
      if ( !DWord )
        return DWord;
      goto LABEL_12;
    }
    byte_1800F2748 = 1;
    if ( !dword_1800EB0C8 )
    {
      LastError = TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
      if ( LastError )
      {
        v4 = "TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation";
        goto LABEL_11;
      }
    }
    DWord = BfeRegQueryDWord(
              v1,
              (unsigned int)L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
              (unsigned int)L"CommitCountThreshold",
              v2,
              (__int64)&dword_1800F2734,
              (__int64)&v6);
    if ( !DWord )
    {
      if ( v6 && dword_1800F2734 )
      {
        qword_1800F2738 = CreateThreadpoolWork((PTP_WORK_CALLBACK)BfeRundownThreadCallback, 0, 0);
        if ( !qword_1800F2738 )
          goto LABEL_10;
        gBfePeriodicRundownEnabled = 1;
      }
      byte_1800F2749 = 1;
      return DWord;
    }
  }
LABEL_12:
  BfeRundownShutdown();
  WfpReportError(DWord, "BfeRundownInit");
  return DWord;
}

```

## disassembly

```asm
0x180046624  push    rbx
0x180046626  sub     rsp, 30h
0x18004662a  lea     rcx, gBfeRundownComponent
0x180046631  mov     [rsp+38h+arg_0], 0
0x180046639  mov     cs:gBfePeriodicRundownEnabled, 0
0x180046643  call    WfpCriticalSectionCreate
0x180046648  mov     rbx, rax
0x18004664b  test    rax, rax
0x18004664e  jnz     loc_180046713
0x180046654  xor     r8d, r8d; pcbe
0x180046657  lea     rcx, BfeEtwCallbackThreadCallback; pfnwk
0x18004665e  xor     edx, edx; pv
0x180046660  call    cs:__imp_CreateThreadpoolWork
0x180046666  mov     cs:qword_1800F2740, rax
0x18004666d  test    rax, rax
0x180046670  jz      loc_1800466F6
0x180046676  mov     eax, cs:dword_1800EB0C8
0x18004667c  mov     cs:byte_1800F2748, 1
0x180046683  test    eax, eax
0x180046685  jnz     short loc_180046699
0x180046687  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x18004668c  test    eax, eax
0x18004668e  jz      short loc_180046699
0x180046690  lea     rdx, aTraceloggingre; "TraceLoggingRegisterEx_EtwEventRegister"...
0x180046697  jmp     short loc_180046703
0x180046699  lea     rax, [rsp+38h+arg_0]
0x18004669e  mov     [rsp+38h+var_10], rax
0x1800466a3  lea     r8, aCommitcountthr; "CommitCountThreshold"
0x1800466aa  lea     rax, dword_1800F2734
0x1800466b1  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\BF"...
0x1800466b8  mov     [rsp+38h+var_18], rax
0x1800466bd  call    BfeRegQueryDWord
0x1800466c2  mov     rbx, rax
0x1800466c5  test    rax, rax
0x1800466c8  jnz     short loc_180046713
0x1800466ca  cmp     [rsp+38h+arg_0], eax
0x1800466ce  jz      short loc_18004673F
0x1800466d0  cmp     cs:dword_1800F2734, eax
0x1800466d6  jbe     short loc_18004673F
0x1800466d8  xor     r8d, r8d; pcbe
0x1800466db  lea     rcx, BfeRundownThreadCallback; pfnwk
0x1800466e2  xor     edx, edx; pv
0x1800466e4  call    cs:__imp_CreateThreadpoolWork
0x1800466ea  mov     cs:qword_1800F2738, rax
0x1800466f1  test    rax, rax
0x1800466f4  jnz     short loc_180046735
0x1800466f6  call    cs:__imp_GetLastError
0x1800466fc  lea     rdx, aBferundowninit; "BfeRundownInit"
0x180046703  mov     r8d, eax
0x180046706  call    WfpReportSysErrorAsWinError
0x18004670b  mov     rbx, rax
0x18004670e  test    rax, rax
0x180046711  jz      short loc_18004672C
0x180046713  call    BfeRundownShutdown
0x180046718  test    rbx, rbx
0x18004671b  jz      short loc_18004672C
0x18004671d  lea     rdx, aBferundowninit; "BfeRundownInit"
0x180046724  mov     rcx, rbx
0x180046727  call    WfpReportError
0x18004672c  mov     rax, rbx
0x18004672f  add     rsp, 30h
0x180046733  pop     rbx
0x180046734  retn
0x180046735  mov     cs:gBfePeriodicRundownEnabled, 1
0x18004673f  mov     cs:byte_1800F2749, 1
0x180046746  jmp     short loc_18004672C
```
