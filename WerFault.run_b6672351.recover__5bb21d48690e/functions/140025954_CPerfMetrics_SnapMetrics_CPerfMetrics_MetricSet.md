# CPerfMetrics::SnapMetrics(CPerfMetrics::MetricSet *)

- ea: `0x140025954`
- end: `0x140025bbc`
- name: `?SnapMetrics@CPerfMetrics@@AEAAXPEAUMetricSet@1@@Z`
- size: `616`
- prototype: `void(CPerfMetrics *__hidden this, struct CPerfMetrics::MetricSet *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140024614`
- `0x14002840c`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140025954`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400259cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400259cc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140025a63`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140025a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025b08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025b08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140025b5d`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x1400259f0`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x1400259f0`
- `ntdll!NtQueryInformationProcess` at `0x140025b2e`
- `ntdll!NtQueryInformationProcess` at `0x140025b83`
- `ntdll!NtQueryInformationProcess` at `0x140025b2e`
- `ntdll!NtQueryInformationProcess` at `0x140025b83`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x140025abc`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x140025abc`

## pseudocode

```c
void __fastcall CPerfMetrics::SnapMetrics(CPerfMetrics *this, struct CPerfMetrics::MetricSet *a2)
{
  HANDLE CurrentThread; // rax
  DWORD dwLowDateTime; // ecx
  HANDLE CurrentProcess; // rax
  DWORD dwHighDateTime; // ecx
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  unsigned __int64 v10; // [rsp+30h] [rbp-79h]
  struct _FILETIME UserTime; // [rsp+38h] [rbp-71h] BYREF
  struct _FILETIME KernelTime; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-61h] BYREF
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-59h] BYREF
  _IO_COUNTERS IoCounters; // [rsp+58h] [rbp-51h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v17; // [rsp+98h] [rbp-11h]
  unsigned int v18; // [rsp+A0h] [rbp-9h]
  unsigned __int64 v19; // [rsp+B0h] [rbp+7h]

  memset_0(a2, 255, 0x70u);
  CreationTime = 0;
  KernelTime = 0;
  UserTime = 0;
  memset(&IoCounters, 0, sizeof(IoCounters));
  memset_0(ProcessInformation, 0, 0x58u);
  v13 = 0;
  CurrentThread = GetCurrentThread();
  if ( GetThreadTimes(CurrentThread, &CreationTime, &CreationTime, &KernelTime, &UserTime) )
  {
    dwLowDateTime = KernelTime.dwLowDateTime;
    HIDWORD(v10) = KernelTime.dwHighDateTime;
    *(_QWORD *)a2 = *(unsigned __int64 *)&UserTime / 0x2710;
    LODWORD(v10) = dwLowDateTime;
    *((_QWORD *)a2 + 1) = v10 / 0x2710;
  }
  CurrentProcess = GetCurrentProcess();
  if ( GetProcessTimes(CurrentProcess, &CreationTime, &CreationTime, &KernelTime, &UserTime) )
  {
    dwHighDateTime = KernelTime.dwHighDateTime;
    *((_QWORD *)a2 + 2) = *(unsigned __int64 *)&UserTime / 0x2710;
    *((_QWORD *)a2 + 3) = __PAIR64__(dwHighDateTime, KernelTime.dwLowDateTime) / 0x2710;
  }
  v7 = GetCurrentProcess();
  if ( GetProcessIoCounters(v7, &IoCounters) )
  {
    *((_QWORD *)a2 + 7) = IoCounters.ReadOperationCount;
    *((_QWORD *)a2 + 8) = IoCounters.WriteOperationCount;
    *((_QWORD *)a2 + 9) = IoCounters.OtherOperationCount;
    *((_QWORD *)a2 + 10) = IoCounters.ReadTransferCount >> 10;
    *((_QWORD *)a2 + 11) = IoCounters.WriteTransferCount >> 10;
    *((_QWORD *)a2 + 12) = IoCounters.OtherTransferCount >> 10;
  }
  v8 = GetCurrentProcess();
  if ( NtQueryInformationProcess(v8, ProcessVmCounters, ProcessInformation, 0x58u, 0) >= 0 )
  {
    *((_QWORD *)a2 + 5) = v17 >> 20;
    *((_QWORD *)a2 + 4) = v19 >> 20;
    *((_QWORD *)a2 + 6) = v18;
  }
  v9 = GetCurrentProcess();
  if ( NtQueryInformationProcess(v9, ProcessHandleCount, &v13, 4u, 0) >= 0 )
    *((_QWORD *)a2 + 13) = v13;
}

```

## disassembly

```asm
0x140025954  mov     [rsp-8+arg_0], rbx
0x140025959  mov     [rsp-8+arg_10], rsi
0x14002595e  push    rbp
0x14002595f  lea     rbp, [rsp-57h]
0x140025964  sub     rsp, 100h
0x14002596b  mov     rax, cs:__security_cookie
0x140025972  xor     rax, rsp
0x140025975  mov     [rbp+57h+var_10], rax
0x140025979  mov     rbx, rdx
0x14002597c  mov     r8d, 70h ; 'p'; Size
0x140025982  mov     rcx, rbx; void *
0x140025985  mov     edx, 0FFh; Val
0x14002598a  call    memset_0
0x14002598f  xorps   xmm0, xmm0
0x140025992  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x14002599a  xor     edx, edx; Val
0x14002599c  mov     qword ptr [rbp+57h+KernelTime.dwLowDateTime], 0
0x1400259a4  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x1400259a8  mov     qword ptr [rbp+57h+UserTime.dwLowDateTime], 0
0x1400259b0  movups  xmmword ptr [rbp+57h+IoCounters.ReadOperationCount], xmm0
0x1400259b4  lea     r8d, [rdx+58h]; Size
0x1400259b8  movups  xmmword ptr [rbp+57h+IoCounters.OtherOperationCount], xmm0
0x1400259bc  movups  xmmword ptr [rbp+57h+IoCounters.WriteTransferCount], xmm0
0x1400259c0  call    memset_0
0x1400259c5  mov     [rbp+57h+var_B8], 0
0x1400259cc  call    cs:__imp_GetCurrentThread
0x1400259d3  nop     dword ptr [rax+rax+00h]
0x1400259d8  mov     rcx, rax; hThread
0x1400259db  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x1400259df  lea     rax, [rbp+57h+UserTime]
0x1400259e3  lea     r8, [rbp+57h+CreationTime]; lpExitTime
0x1400259e7  mov     [rsp+100h+lpUserTime], rax; lpUserTime
0x1400259ec  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1400259f0  call    cs:__imp_GetThreadTimes
0x1400259f7  nop     dword ptr [rax+rax+00h]
0x1400259fc  mov     rsi, 346DC5D63886594Bh
0x140025a06  test    eax, eax
0x140025a08  jz      short loc_140025A3F
0x140025a0a  mov     eax, [rbp+57h+UserTime.dwHighDateTime]
0x140025a0d  mov     ecx, [rbp+57h+UserTime.dwLowDateTime]
0x140025a10  mov     dword ptr [rbp+57h+var_D0+4], eax
0x140025a13  mov     rax, rsi
0x140025a16  mov     dword ptr [rbp+57h+var_D0], ecx
0x140025a19  mul     [rbp+57h+var_D0]
0x140025a1d  mov     eax, [rbp+57h+KernelTime.dwHighDateTime]
0x140025a20  mov     ecx, [rbp+57h+KernelTime.dwLowDateTime]
0x140025a23  shr     rdx, 0Bh
0x140025a27  mov     dword ptr [rbp+57h+var_D0+4], eax
0x140025a2a  mov     rax, rsi
0x140025a2d  mov     [rbx], rdx
0x140025a30  mov     dword ptr [rbp+57h+var_D0], ecx
0x140025a33  mul     [rbp+57h+var_D0]
0x140025a37  shr     rdx, 0Bh
0x140025a3b  mov     [rbx+8], rdx
0x140025a3f  call    cs:__imp_GetCurrentProcess
0x140025a46  nop     dword ptr [rax+rax+00h]
0x140025a4b  mov     rcx, rax; hProcess
0x140025a4e  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x140025a52  lea     rax, [rbp+57h+UserTime]
0x140025a56  lea     r8, [rbp+57h+CreationTime]; lpExitTime
0x140025a5a  mov     [rsp+100h+lpUserTime], rax; lpUserTime
0x140025a5f  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140025a63  call    cs:__imp_GetProcessTimes
0x140025a6a  nop     dword ptr [rax+rax+00h]
0x140025a6f  test    eax, eax
0x140025a71  jz      short loc_140025AA9
0x140025a73  mov     edx, [rbp+57h+UserTime.dwLowDateTime]
0x140025a76  mov     rax, rsi
0x140025a79  mov     ecx, [rbp+57h+UserTime.dwHighDateTime]
0x140025a7c  mov     dword ptr [rbp+57h+var_D0], edx
0x140025a7f  mov     dword ptr [rbp+57h+var_D0+4], ecx
0x140025a82  mul     [rbp+57h+var_D0]
0x140025a86  mov     ecx, [rbp+57h+KernelTime.dwHighDateTime]
0x140025a89  mov     rax, rsi
0x140025a8c  shr     rdx, 0Bh
0x140025a90  mov     [rbx+10h], rdx
0x140025a94  mov     edx, [rbp+57h+KernelTime.dwLowDateTime]
0x140025a97  mov     dword ptr [rbp+57h+var_D0], edx
0x140025a9a  mov     dword ptr [rbp+57h+var_D0+4], ecx
0x140025a9d  mul     [rbp+57h+var_D0]
0x140025aa1  shr     rdx, 0Bh
0x140025aa5  mov     [rbx+18h], rdx
0x140025aa9  call    cs:__imp_GetCurrentProcess
0x140025ab0  nop     dword ptr [rax+rax+00h]
0x140025ab5  mov     rcx, rax; hProcess
0x140025ab8  lea     rdx, [rbp+57h+IoCounters]; lpIoCounters
0x140025abc  call    cs:__imp_GetProcessIoCounters
0x140025ac3  nop     dword ptr [rax+rax+00h]
0x140025ac8  test    eax, eax
0x140025aca  jz      short loc_140025B08
0x140025acc  mov     rax, [rbp+57h+IoCounters.ReadOperationCount]
0x140025ad0  mov     [rbx+38h], rax
0x140025ad4  mov     rax, [rbp+57h+IoCounters.WriteOperationCount]
0x140025ad8  mov     [rbx+40h], rax
0x140025adc  mov     rax, [rbp+57h+IoCounters.OtherOperationCount]
0x140025ae0  mov     [rbx+48h], rax
0x140025ae4  mov     rax, [rbp+57h+IoCounters.ReadTransferCount]
0x140025ae8  shr     rax, 0Ah
0x140025aec  mov     [rbx+50h], rax
0x140025af0  mov     rax, [rbp+57h+IoCounters.WriteTransferCount]
0x140025af4  shr     rax, 0Ah
0x140025af8  mov     [rbx+58h], rax
0x140025afc  mov     rax, [rbp+57h+IoCounters.OtherTransferCount]
0x140025b00  shr     rax, 0Ah
0x140025b04  mov     [rbx+60h], rax
0x140025b08  call    cs:__imp_GetCurrentProcess
0x140025b0f  nop     dword ptr [rax+rax+00h]
0x140025b14  mov     r9d, 58h ; 'X'; ProcessInformationLength
0x140025b1a  mov     [rsp+100h+lpUserTime], 0; ReturnLength
0x140025b23  mov     rcx, rax; ProcessHandle
0x140025b26  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x140025b2a  lea     edx, [r9-55h]; ProcessInformationClass
0x140025b2e  call    cs:__imp_NtQueryInformationProcess
0x140025b35  nop     dword ptr [rax+rax+00h]
0x140025b3a  test    eax, eax
0x140025b3c  js      short loc_140025B5D
0x140025b3e  mov     rax, [rbp+57h+var_68]
0x140025b42  shr     rax, 14h
0x140025b46  mov     [rbx+28h], rax
0x140025b4a  mov     rax, [rbp+57h+var_50]
0x140025b4e  shr     rax, 14h
0x140025b52  mov     [rbx+20h], rax
0x140025b56  mov     eax, [rbp+57h+var_60]
0x140025b59  mov     [rbx+30h], rax
0x140025b5d  call    cs:__imp_GetCurrentProcess
0x140025b64  nop     dword ptr [rax+rax+00h]
0x140025b69  mov     r9d, 4; ProcessInformationLength
0x140025b6f  mov     [rsp+100h+lpUserTime], 0; ReturnLength
0x140025b78  mov     rcx, rax; ProcessHandle
0x140025b7b  lea     r8, [rbp+57h+var_B8]; ProcessInformation
0x140025b7f  lea     edx, [r9+10h]; ProcessInformationClass
0x140025b83  call    cs:__imp_NtQueryInformationProcess
0x140025b8a  nop     dword ptr [rax+rax+00h]
0x140025b8f  test    eax, eax
0x140025b91  js      short loc_140025B9A
0x140025b93  mov     eax, [rbp+57h+var_B8]
0x140025b96  mov     [rbx+68h], rax
0x140025b9a  mov     rcx, [rbp+57h+var_10]
0x140025b9e  xor     rcx, rsp; StackCookie
0x140025ba1  call    __security_check_cookie
0x140025ba6  lea     r11, [rsp+100h+var_s0]
0x140025bae  mov     rbx, [r11+10h]
0x140025bb2  mov     rsi, [r11+20h]
0x140025bb6  mov     rsp, r11
0x140025bb9  pop     rbp
0x140025bba  retn
```
