# BfePerfMonAddSingleton

- ea: `0x180048a48`
- end: `0x180048ada`
- name: `BfePerfMonAddSingleton`
- size: `146`
- prototype: `__int64 __fastcall(HANDLE ProviderHandle, LPCGUID CounterSetGuid)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180075b5c`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180048a48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a9a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180048a86`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180048a86`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x180048a5b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x180048a5b`

## string_xrefs

- `0x180048aa6`: `PerfCreateInstance`

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
0x180048a48  push    rbx
0x180048a4a  push    rsi
0x180048a4b  push    rdi
0x180048a4c  push    r14
0x180048a4e  sub     rsp, 28h
0x180048a52  mov     r14, r9
0x180048a55  mov     rdi, rdx
0x180048a58  mov     rsi, rcx
0x180048a5b  call    cs:__imp_PerfSetCounterSetInfo
0x180048a62  nop     dword ptr [rax+rax+00h]
0x180048a67  test    eax, eax
0x180048a69  jz      short loc_180048A74
0x180048a6b  lea     rdx, aPerfsetcounter; "PerfSetCounterSetInfo"
0x180048a72  jmp     short loc_180048AAD
0x180048a74  xor     r9d, r9d; Id
0x180048a77  lea     r8, Name; "_Default"
0x180048a7e  mov     rdx, rdi; CounterSetGuid
0x180048a81  mov     rcx, rsi; ProviderHandle
0x180048a84  xor     ebx, ebx
0x180048a86  call    cs:__imp_PerfCreateInstance
0x180048a8d  nop     dword ptr [rax+rax+00h]
0x180048a92  mov     [r14], rax
0x180048a95  test    rax, rax
0x180048a98  jnz     short loc_180048ACC
0x180048a9a  call    cs:__imp_GetLastError
0x180048aa1  nop     dword ptr [rax+rax+00h]
0x180048aa6  lea     rdx, aPerfcreateinst; "PerfCreateInstance"
0x180048aad  mov     r8d, eax
0x180048ab0  call    WfpReportSysErrorAsWinError
0x180048ab5  mov     rbx, rax
0x180048ab8  test    rax, rax
0x180048abb  jz      short loc_180048ACC
0x180048abd  lea     rdx, aBfeperfmonadds; "BfePerfMonAddSingleton"
0x180048ac4  mov     rcx, rax
0x180048ac7  call    WfpReportError
0x180048acc  mov     rax, rbx
0x180048acf  add     rsp, 28h
0x180048ad3  pop     r14
0x180048ad5  pop     rdi
0x180048ad6  pop     rsi
0x180048ad7  pop     rbx
0x180048ad8  retn
```
