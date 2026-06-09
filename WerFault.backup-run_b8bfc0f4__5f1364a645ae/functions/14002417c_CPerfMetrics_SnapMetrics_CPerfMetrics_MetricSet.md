# CPerfMetrics::SnapMetrics(CPerfMetrics::MetricSet *)

- ea: `0x14002417c`
- end: `0x1400243a7`
- name: `?SnapMetrics@CPerfMetrics@@AEAAXPEAUMetricSet@1@@Z`
- size: `555`
- prototype: `void(CPerfMetrics *__hidden this, struct CPerfMetrics::MetricSet *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140022ef4`
- `0x140026a70`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14002417c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400241f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400241f4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140024279`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140024279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002425b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400242b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002430c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002425b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400242b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002430c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024355`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x140024212`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x140024212`
- `ntdll!NtQueryInformationProcess` at `0x14002432c`
- `ntdll!NtQueryInformationProcess` at `0x140024375`
- `ntdll!NtQueryInformationProcess` at `0x14002432c`
- `ntdll!NtQueryInformationProcess` at `0x140024375`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x1400242c6`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x1400242c6`

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
0x14002417c  mov     [rsp-8+arg_0], rbx
0x140024181  mov     [rsp-8+arg_10], rsi
0x140024186  push    rbp
0x140024187  lea     rbp, [rsp-57h]
0x14002418c  sub     rsp, 100h
0x140024193  mov     rax, cs:__security_cookie
0x14002419a  xor     rax, rsp
0x14002419d  mov     [rbp+57h+var_10], rax
0x1400241a1  mov     rbx, rdx
0x1400241a4  mov     r8d, 70h ; 'p'; Size
0x1400241aa  mov     rcx, rbx; void *
0x1400241ad  mov     edx, 0FFh; Val
0x1400241b2  call    memset_0
0x1400241b7  xorps   xmm0, xmm0
0x1400241ba  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], 0
0x1400241c2  xor     edx, edx; Val
0x1400241c4  mov     qword ptr [rbp+57h+KernelTime.dwLowDateTime], 0
0x1400241cc  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x1400241d0  mov     qword ptr [rbp+57h+UserTime.dwLowDateTime], 0
0x1400241d8  movups  xmmword ptr [rbp+57h+IoCounters.ReadOperationCount], xmm0
0x1400241dc  lea     r8d, [rdx+58h]; Size
0x1400241e0  movups  xmmword ptr [rbp+57h+IoCounters.OtherOperationCount], xmm0
0x1400241e4  movups  xmmword ptr [rbp+57h+IoCounters.WriteTransferCount], xmm0
0x1400241e8  call    memset_0
0x1400241ed  mov     [rbp+57h+var_B8], 0
0x1400241f4  call    cs:__imp_GetCurrentThread
0x1400241fa  mov     rcx, rax; hThread
0x1400241fd  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x140024201  lea     rax, [rbp+57h+UserTime]
0x140024205  lea     r8, [rbp+57h+CreationTime]; lpExitTime
0x140024209  mov     [rsp+100h+lpUserTime], rax; lpUserTime
0x14002420e  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140024212  call    cs:__imp_GetThreadTimes
0x140024218  mov     rsi, 346DC5D63886594Bh
0x140024222  test    eax, eax
0x140024224  jz      short loc_14002425B
0x140024226  mov     eax, [rbp+57h+UserTime.dwHighDateTime]
0x140024229  mov     ecx, [rbp+57h+UserTime.dwLowDateTime]
0x14002422c  mov     dword ptr [rbp+57h+var_D0+4], eax
0x14002422f  mov     rax, rsi
0x140024232  mov     dword ptr [rbp+57h+var_D0], ecx
0x140024235  mul     [rbp+57h+var_D0]
0x140024239  mov     eax, [rbp+57h+KernelTime.dwHighDateTime]
0x14002423c  mov     ecx, [rbp+57h+KernelTime.dwLowDateTime]
0x14002423f  shr     rdx, 0Bh
0x140024243  mov     dword ptr [rbp+57h+var_D0+4], eax
0x140024246  mov     rax, rsi
0x140024249  mov     [rbx], rdx
0x14002424c  mov     dword ptr [rbp+57h+var_D0], ecx
0x14002424f  mul     [rbp+57h+var_D0]
0x140024253  shr     rdx, 0Bh
0x140024257  mov     [rbx+8], rdx
0x14002425b  call    cs:__imp_GetCurrentProcess
0x140024261  mov     rcx, rax; hProcess
0x140024264  lea     r9, [rbp+57h+KernelTime]; lpKernelTime
0x140024268  lea     rax, [rbp+57h+UserTime]
0x14002426c  lea     r8, [rbp+57h+CreationTime]; lpExitTime
0x140024270  mov     [rsp+100h+lpUserTime], rax; lpUserTime
0x140024275  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x140024279  call    cs:__imp_GetProcessTimes
0x14002427f  test    eax, eax
0x140024281  jz      short loc_1400242B9
0x140024283  mov     edx, [rbp+57h+UserTime.dwLowDateTime]
0x140024286  mov     rax, rsi
0x140024289  mov     ecx, [rbp+57h+UserTime.dwHighDateTime]
0x14002428c  mov     dword ptr [rbp+57h+var_D0], edx
0x14002428f  mov     dword ptr [rbp+57h+var_D0+4], ecx
0x140024292  mul     [rbp+57h+var_D0]
0x140024296  mov     ecx, [rbp+57h+KernelTime.dwHighDateTime]
0x140024299  mov     rax, rsi
0x14002429c  shr     rdx, 0Bh
0x1400242a0  mov     [rbx+10h], rdx
0x1400242a4  mov     edx, [rbp+57h+KernelTime.dwLowDateTime]
0x1400242a7  mov     dword ptr [rbp+57h+var_D0], edx
0x1400242aa  mov     dword ptr [rbp+57h+var_D0+4], ecx
0x1400242ad  mul     [rbp+57h+var_D0]
0x1400242b1  shr     rdx, 0Bh
0x1400242b5  mov     [rbx+18h], rdx
0x1400242b9  call    cs:__imp_GetCurrentProcess
0x1400242bf  mov     rcx, rax; hProcess
0x1400242c2  lea     rdx, [rbp+57h+IoCounters]; lpIoCounters
0x1400242c6  call    cs:__imp_GetProcessIoCounters
0x1400242cc  test    eax, eax
0x1400242ce  jz      short loc_14002430C
0x1400242d0  mov     rax, [rbp+57h+IoCounters.ReadOperationCount]
0x1400242d4  mov     [rbx+38h], rax
0x1400242d8  mov     rax, [rbp+57h+IoCounters.WriteOperationCount]
0x1400242dc  mov     [rbx+40h], rax
0x1400242e0  mov     rax, [rbp+57h+IoCounters.OtherOperationCount]
0x1400242e4  mov     [rbx+48h], rax
0x1400242e8  mov     rax, [rbp+57h+IoCounters.ReadTransferCount]
0x1400242ec  shr     rax, 0Ah
0x1400242f0  mov     [rbx+50h], rax
0x1400242f4  mov     rax, [rbp+57h+IoCounters.WriteTransferCount]
0x1400242f8  shr     rax, 0Ah
0x1400242fc  mov     [rbx+58h], rax
0x140024300  mov     rax, [rbp+57h+IoCounters.OtherTransferCount]
0x140024304  shr     rax, 0Ah
0x140024308  mov     [rbx+60h], rax
0x14002430c  call    cs:__imp_GetCurrentProcess
0x140024312  mov     r9d, 58h ; 'X'; ProcessInformationLength
0x140024318  mov     [rsp+100h+lpUserTime], 0; ReturnLength
0x140024321  mov     rcx, rax; ProcessHandle
0x140024324  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x140024328  lea     edx, [r9-55h]; ProcessInformationClass
0x14002432c  call    cs:__imp_NtQueryInformationProcess
0x140024332  test    eax, eax
0x140024334  js      short loc_140024355
0x140024336  mov     rax, [rbp+57h+var_68]
0x14002433a  shr     rax, 14h
0x14002433e  mov     [rbx+28h], rax
0x140024342  mov     rax, [rbp+57h+var_50]
0x140024346  shr     rax, 14h
0x14002434a  mov     [rbx+20h], rax
0x14002434e  mov     eax, [rbp+57h+var_60]
0x140024351  mov     [rbx+30h], rax
0x140024355  call    cs:__imp_GetCurrentProcess
0x14002435b  mov     r9d, 4; ProcessInformationLength
0x140024361  mov     [rsp+100h+lpUserTime], 0; ReturnLength
0x14002436a  mov     rcx, rax; ProcessHandle
0x14002436d  lea     r8, [rbp+57h+var_B8]; ProcessInformation
0x140024371  lea     edx, [r9+10h]; ProcessInformationClass
0x140024375  call    cs:__imp_NtQueryInformationProcess
0x14002437b  test    eax, eax
0x14002437d  js      short loc_140024386
0x14002437f  mov     eax, [rbp+57h+var_B8]
0x140024382  mov     [rbx+68h], rax
0x140024386  mov     rcx, [rbp+57h+var_10]
0x14002438a  xor     rcx, rsp; StackCookie
0x14002438d  call    __security_check_cookie
0x140024392  lea     r11, [rsp+100h+var_s0]
0x14002439a  mov     rbx, [r11+10h]
0x14002439e  mov     rsi, [r11+20h]
0x1400243a2  mov     rsp, r11
0x1400243a5  pop     rbp
0x1400243a6  retn
```
