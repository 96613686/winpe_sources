# BfePerfMonAddSingleton

- ea: `0x180046ba4`
- end: `0x180046c23`
- name: `BfePerfMonAddSingleton`
- size: `127`
- prototype: `__int64 __fastcall(HANDLE ProviderHandle, LPCGUID CounterSetGuid)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180073250`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180046ba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046bea`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180046bdc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180046bdc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x180046bb7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x180046bb7`

## string_xrefs

- `0x180046bf0`: `PerfCreateInstance`

## pseudocode

```c
__int64 __fastcall BfePerfMonAddSingleton(
        HANDLE ProviderHandle,
        struct _PERF_COUNTERSET_INFO *CounterSetGuid,
        ULONG a3,
        PPERF_COUNTERSET_INSTANCE *a4)
{
  ULONG LastError; // eax
  __int64 v8; // rcx
  const char *v9; // rdx
  __int64 v10; // rbx
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  __int64 v12; // rax

  LastError = PerfSetCounterSetInfo(ProviderHandle, CounterSetGuid, a3);
  if ( LastError )
  {
    v9 = "PerfSetCounterSetInfo";
  }
  else
  {
    v10 = 0;
    Instance = PerfCreateInstance(ProviderHandle, &CounterSetGuid->CounterSetGuid, L"_Default", 0);
    *a4 = Instance;
    if ( Instance )
      return v10;
    LastError = GetLastError();
    v9 = "PerfCreateInstance";
  }
  v12 = WfpReportSysErrorAsWinError(v8, v9, LastError);
  v10 = v12;
  if ( v12 )
    WfpReportError(v12, "BfePerfMonAddSingleton");
  return v10;
}

```

## disassembly

```asm
0x180046ba4  push    rbx
0x180046ba6  push    rsi
0x180046ba7  push    rdi
0x180046ba8  push    r14
0x180046baa  sub     rsp, 28h
0x180046bae  mov     r14, r9
0x180046bb1  mov     rdi, rdx
0x180046bb4  mov     rsi, rcx
0x180046bb7  call    cs:__imp_PerfSetCounterSetInfo
0x180046bbd  test    eax, eax
0x180046bbf  jz      short loc_180046BCA
0x180046bc1  lea     rdx, aPerfsetcounter; "PerfSetCounterSetInfo"
0x180046bc8  jmp     short loc_180046BF7
0x180046bca  xor     r9d, r9d; Id
0x180046bcd  lea     r8, Name; "_Default"
0x180046bd4  mov     rdx, rdi; CounterSetGuid
0x180046bd7  mov     rcx, rsi; ProviderHandle
0x180046bda  xor     ebx, ebx
0x180046bdc  call    cs:__imp_PerfCreateInstance
0x180046be2  mov     [r14], rax
0x180046be5  test    rax, rax
0x180046be8  jnz     short loc_180046C16
0x180046bea  call    cs:__imp_GetLastError
0x180046bf0  lea     rdx, aPerfcreateinst; "PerfCreateInstance"
0x180046bf7  mov     r8d, eax
0x180046bfa  call    WfpReportSysErrorAsWinError
0x180046bff  mov     rbx, rax
0x180046c02  test    rax, rax
0x180046c05  jz      short loc_180046C16
0x180046c07  lea     rdx, aBfeperfmonadds; "BfePerfMonAddSingleton"
0x180046c0e  mov     rcx, rax
0x180046c11  call    WfpReportError
0x180046c16  mov     rax, rbx
0x180046c19  add     rsp, 28h
0x180046c1d  pop     r14
0x180046c1f  pop     rdi
0x180046c20  pop     rsi
0x180046c21  pop     rbx
0x180046c22  retn
```
