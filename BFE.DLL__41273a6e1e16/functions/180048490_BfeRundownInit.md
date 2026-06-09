# BfeRundownInit

- ea: `0x180048490`
- end: `0x1800485c7`
- name: `BfeRundownInit`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004ec9c`

## callees

- `0x180004798`
- `0x180012d8c`
- `0x1800197d0`
- `0x180031694`
- `0x180048490`
- `0x180048ca4`
- `0x180076164`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800484cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180048556`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800484cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180048556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004856e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004856e`

## string_xrefs

- `0x180048523`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x180048515`: `CommitCountThreshold`

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
    qword_1800F5760 = CreateThreadpoolWork(BfeEtwCallbackThreadCallback, 0, 0);
    if ( !qword_1800F5760 )
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
    byte_1800F5768 = 1;
    if ( !dword_1800EE0C8 )
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
              (__int64)&dword_1800F5754,
              (__int64)&v6);
    if ( !DWord )
    {
      if ( v6 && dword_1800F5754 )
      {
        qword_1800F5758 = CreateThreadpoolWork(BfeRundownThreadCallback, 0, 0);
        if ( !qword_1800F5758 )
          goto LABEL_10;
        gBfePeriodicRundownEnabled = 1;
      }
      byte_1800F5769 = 1;
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
0x180048490  push    rbx
0x180048492  sub     rsp, 30h
0x180048496  lea     rcx, gBfeRundownComponent
0x18004849d  mov     [rsp+38h+arg_0], 0
0x1800484a5  mov     cs:gBfePeriodicRundownEnabled, 0
0x1800484af  call    WfpCriticalSectionCreate
0x1800484b4  mov     rbx, rax
0x1800484b7  test    rax, rax
0x1800484ba  jnz     loc_180048591
0x1800484c0  xor     r8d, r8d; pcbe
0x1800484c3  lea     rcx, BfeEtwCallbackThreadCallback; pfnwk
0x1800484ca  xor     edx, edx; pv
0x1800484cc  call    cs:__imp_CreateThreadpoolWork
0x1800484d3  nop     dword ptr [rax+rax+00h]
0x1800484d8  mov     cs:qword_1800F5760, rax
0x1800484df  test    rax, rax
0x1800484e2  jz      loc_18004856E
0x1800484e8  mov     eax, cs:dword_1800EE0C8
0x1800484ee  mov     cs:byte_1800F5768, 1
0x1800484f5  test    eax, eax
0x1800484f7  jnz     short loc_18004850B
0x1800484f9  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x1800484fe  test    eax, eax
0x180048500  jz      short loc_18004850B
0x180048502  lea     rdx, aTraceloggingre; "TraceLoggingRegisterEx_EtwEventRegister"...
0x180048509  jmp     short loc_180048581
0x18004850b  lea     rax, [rsp+38h+arg_0]
0x180048510  mov     [rsp+38h+var_10], rax
0x180048515  lea     r8, aCommitcountthr; "CommitCountThreshold"
0x18004851c  lea     rax, dword_1800F5754
0x180048523  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\BF"...
0x18004852a  mov     [rsp+38h+var_18], rax
0x18004852f  call    BfeRegQueryDWord
0x180048534  mov     rbx, rax
0x180048537  test    rax, rax
0x18004853a  jnz     short loc_180048591
0x18004853c  cmp     [rsp+38h+arg_0], eax
0x180048540  jz      short loc_1800485BE
0x180048542  cmp     cs:dword_1800F5754, eax
0x180048548  jbe     short loc_1800485BE
0x18004854a  xor     r8d, r8d; pcbe
0x18004854d  lea     rcx, BfeRundownThreadCallback; pfnwk
0x180048554  xor     edx, edx; pv
0x180048556  call    cs:__imp_CreateThreadpoolWork
0x18004855d  nop     dword ptr [rax+rax+00h]
0x180048562  mov     cs:qword_1800F5758, rax
0x180048569  test    rax, rax
0x18004856c  jnz     short loc_1800485B4
0x18004856e  call    cs:__imp_GetLastError
0x180048575  nop     dword ptr [rax+rax+00h]
0x18004857a  lea     rdx, aBferundowninit; "BfeRundownInit"
0x180048581  mov     r8d, eax
0x180048584  call    WfpReportSysErrorAsWinError
0x180048589  mov     rbx, rax
0x18004858c  test    rax, rax
0x18004858f  jz      short loc_1800485AA
0x180048591  call    BfeRundownShutdown
0x180048596  test    rbx, rbx
0x180048599  jz      short loc_1800485AA
0x18004859b  lea     rdx, aBferundowninit; "BfeRundownInit"
0x1800485a2  mov     rcx, rbx
0x1800485a5  call    WfpReportError
0x1800485aa  mov     rax, rbx
0x1800485ad  add     rsp, 30h
0x1800485b1  pop     rbx
0x1800485b2  retn
0x1800485b4  mov     cs:gBfePeriodicRundownEnabled, 1
0x1800485be  mov     cs:byte_1800F5769, 1
0x1800485c5  jmp     short loc_1800485AA
```
