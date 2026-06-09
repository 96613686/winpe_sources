# CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(void)

- ea: `0x14000a130`
- end: `0x14000a40c`
- name: `?PerfSet_Health_Data@CInterceptor_IWbemSyncProvider@@QEAAPEAXXZ`
- size: `732`
- prototype: `void *__fastcall(CInterceptor_IWbemSyncProvider *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140008760`
- `0x140008960`
- `0x140008b50`
- `0x140008f30`
- `0x1400248f0`

## callees

- `0x14000a0f0`
- `0x14000a130`
- `0x14000a414`
- `0x14000a530`
- `0x140027328`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x14000a2eb`
- `ntdll!NtQuerySystemInformation` at `0x14000a2eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000a3c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000a3c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000a26c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000a26c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a3ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a3ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a2c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a2c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a282`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000a3b4`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000a3eb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000a3b4`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000a3eb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000a375`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000a393`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000a375`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000a393`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000a180`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000a180`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x14000a223`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x14000a223`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x14000a23f`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x14000a23f`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x14000a20a`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x14000a20a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CInterceptor_IWbemSyncProvider::PerfSet_Health_Data(CInterceptor_IWbemSyncProvider *this)
{
  struct _FILETIME v2; // rdi
  int v3; // r12d
  unsigned __int64 v4; // rcx
  ULONGLONG *v5; // rbx
  DWORD CurrentProcessId; // ecx
  ULONG v7; // r14d
  int v8; // r15d
  NTSTATUS v9; // eax
  _QWORD v11[4]; // [rsp+20h] [rbp-20h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+40h] BYREF

  if ( CInterceptor_IWbemSyncProvider::s_ConsoleDisplayState )
  {
    if ( *((_QWORD *)this + 68) )
    {
      if ( *((_DWORD *)this + 147) )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v2 = SystemTimeAsFileTime;
        if ( (unsigned __int64)qword_140060940 <= *(_QWORD *)&SystemTimeAsFileTime - *((_QWORD *)this + 70) )
        {
          v3 = 1;
          _InterlockedExchange64((volatile __int64 *)this + 70, *(_QWORD *)&SystemTimeAsFileTime);
          CInterceptor_IWbemSyncProvider::RefreshCPURawData(this);
          ReturnLength = 0;
          v4 = CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp;
          if ( *(_QWORD *)&v2 - CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp > 0x11E1A300 )
          {
            qword_140060938 /= 0x2710uLL;
            Registry::Registry((Registry *)v11, L"Software\\Microsoft\\WBEM\\Tracing\\Providers", 3u);
            Registry::GetDWORD((Registry *)v11, L"ProcessDataInterval_ms", (unsigned int *)&qword_140060938);
            qword_140060938 *= 10000;
            Registry::~Registry((Registry *)v11);
            v4 = CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp;
          }
          if ( qword_140060938 >= *(_QWORD *)&v2 - v4 && CInterceptor_IWbemSyncProvider::s_pProcessDATA )
          {
            AcquireSRWLockShared(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
            v5 = (ULONGLONG *)CInterceptor_IWbemSyncProvider::s_pProcessDATA;
          }
          else
          {
            v7 = 1572864;
            _InterlockedExchange64(
              (volatile __int64 *)&CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp,
              *(_QWORD *)&v2);
            AcquireSRWLockExclusive(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
            v5 = (ULONGLONG *)operator new(0x180000u);
            v8 = 1;
            while ( v8 )
            {
              v9 = NtQuerySystemInformation(SystemProcessInformation, v5, v7, &ReturnLength);
              if ( v9 == -1073741820 )
              {
                operator delete(v5);
                v7 = ReturnLength + 0x8000;
                v5 = (ULONGLONG *)operator new(ReturnLength + 0x8000);
                if ( !v5 )
                  goto LABEL_26;
              }
              else
              {
                if ( v9 < 0 )
                {
                  operator delete(v5);
                  goto LABEL_26;
                }
                v8 = 0;
                v3 = 0;
                v11[0] = CInterceptor_IWbemSyncProvider::s_pProcessDATA;
                v11[1] = 0;
                CInterceptor_IWbemSyncProvider::s_pProcessDATA = v5;
                CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>((__int64)v11);
              }
            }
          }
          if ( v5 )
          {
            CurrentProcessId = GetCurrentProcessId();
            while ( v5 )
            {
              if ( *((_DWORD *)v5 + 20) == CurrentProcessId )
              {
                PerfSetULongCounterValue(
                  WmiprvSePerfCounter,
                  *((PPERF_COUNTERSET_INSTANCE *)this + 68),
                  2u,
                  *((_DWORD *)v5 + 24));
                PerfSetULongCounterValue(
                  WmiprvSePerfCounter,
                  *((PPERF_COUNTERSET_INSTANCE *)this + 68),
                  3u,
                  *((_DWORD *)v5 + 1));
                PerfSetULongLongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 4u, v5[25]);
                break;
              }
              if ( *(_DWORD *)v5 )
                v5 = (ULONGLONG *)((char *)v5 + *(unsigned int *)v5);
              else
                v5 = 0;
            }
          }
LABEL_26:
          if ( v3 )
            ReleaseSRWLockShared(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
          else
            ReleaseSRWLockExclusive(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
          PerfSetULongLongCounterValue(
            WmiprvSePerfCounter,
            *((PPERF_COUNTERSET_INSTANCE *)this + 68),
            0xBu,
            *(_QWORD *)&v2);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000a130  mov     [rsp-28h+arg_0], rbx
0x14000a135  mov     [rsp-28h+arg_18], rsi
0x14000a13a  push    rbp
0x14000a13b  push    rdi
0x14000a13c  push    r12
0x14000a13e  push    r14
0x14000a140  push    r15
0x14000a142  mov     rbp, rsp
0x14000a145  sub     rsp, 40h
0x14000a149  mov     rsi, rcx
0x14000a14c  cmp     cs:?s_ConsoleDisplayState@CInterceptor_IWbemSyncProvider@@0W4_MONITOR_DISPLAY_STATE@@A, 0; _MONITOR_DISPLAY_STATE CInterceptor_IWbemSyncProvider::s_ConsoleDisplayState
0x14000a153  jz      loc_14000A3F1
0x14000a159  cmp     qword ptr [rcx+220h], 0
0x14000a161  jz      loc_14000A3F1
0x14000a167  cmp     dword ptr [rcx+24Ch], 0
0x14000a16e  jz      loc_14000A3F1
0x14000a174  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14000a17c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000a180  call    cs:__imp_GetSystemTimeAsFileTime
0x14000a186  mov     edi, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x14000a189  shl     rdi, 20h
0x14000a18d  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000a190  or      rdi, rax
0x14000a193  mov     rax, rdi
0x14000a196  sub     rax, [rsi+230h]
0x14000a19d  cmp     cs:qword_140060940, rax
0x14000a1a4  ja      loc_14000A3F1
0x14000a1aa  mov     r12d, 1
0x14000a1b0  mov     rax, rdi
0x14000a1b3  xchg    rax, [rsi+230h]
0x14000a1ba  mov     rcx, rsi; this
0x14000a1bd  call    ?RefreshCPURawData@CInterceptor_IWbemSyncProvider@@QEAAJXZ; CInterceptor_IWbemSyncProvider::RefreshCPURawData(void)
0x14000a1c2  mov     [rbp+ReturnLength], 0
0x14000a1c9  mov     rax, rdi
0x14000a1cc  mov     rcx, cs:?s_ulProcessDATATimestamp@CInterceptor_IWbemSyncProvider@@0_KA; unsigned __int64 CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp
0x14000a1d3  sub     rax, rcx
0x14000a1d6  cmp     rax, 11E1A300h
0x14000a1dc  jbe     short loc_14000A24C
0x14000a1de  mov     rax, 346DC5D63886594Bh
0x14000a1e8  mul     cs:qword_140060938
0x14000a1ef  shr     rdx, 0Bh
0x14000a1f3  mov     cs:qword_140060938, rdx
0x14000a1fa  lea     r8d, [r12+2]
0x14000a1ff  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\Tracing\\Pro"...
0x14000a206  lea     rcx, [rbp+var_20]
0x14000a20a  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x14000a210  nop
0x14000a211  lea     r8, qword_140060938
0x14000a218  lea     rdx, aProcessdataint; "ProcessDataInterval_ms"
0x14000a21f  lea     rcx, [rbp+var_20]
0x14000a223  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x14000a229  imul    rax, cs:qword_140060938, 2710h
0x14000a234  mov     cs:qword_140060938, rax
0x14000a23b  lea     rcx, [rbp+var_20]
0x14000a23f  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x14000a245  mov     rcx, cs:?s_ulProcessDATATimestamp@CInterceptor_IWbemSyncProvider@@0_KA; unsigned __int64 CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp
0x14000a24c  mov     rax, rdi
0x14000a24f  sub     rax, rcx
0x14000a252  cmp     cs:qword_140060938, rax
0x14000a259  jb      short loc_14000A2AC
0x14000a25b  cmp     cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA, 0; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x14000a263  jz      short loc_14000A2AC
0x14000a265  lea     rcx, ?s_ProcessDATALock@CInterceptor_IWbemSyncProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x14000a26c  call    cs:__imp_AcquireSRWLockShared
0x14000a272  mov     rbx, cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x14000a279  test    rbx, rbx
0x14000a27c  jz      loc_14000A3BA
0x14000a282  call    cs:__imp_GetCurrentProcessId
0x14000a288  mov     ecx, eax
0x14000a28a  test    rbx, rbx
0x14000a28d  jz      loc_14000A3BA
0x14000a293  cmp     [rbx+50h], ecx
0x14000a296  jz      loc_14000A35D
0x14000a29c  cmp     dword ptr [rbx], 0
0x14000a29f  jz      loc_14000A356
0x14000a2a5  mov     eax, [rbx]
0x14000a2a7  add     rbx, rax
0x14000a2aa  jmp     short loc_14000A28A
0x14000a2ac  mov     r14d, 180000h
0x14000a2b2  mov     rax, rdi
0x14000a2b5  xchg    rax, cs:?s_ulProcessDATATimestamp@CInterceptor_IWbemSyncProvider@@0_KA; unsigned __int64 CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp
0x14000a2bc  lea     rcx, ?s_ProcessDATALock@CInterceptor_IWbemSyncProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x14000a2c3  call    cs:__imp_AcquireSRWLockExclusive
0x14000a2c9  mov     ecx, r14d; dwBytes
0x14000a2cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a2d1  mov     rbx, rax
0x14000a2d4  mov     r15d, r12d
0x14000a2d7  test    r15d, r15d
0x14000a2da  jz      short loc_14000A279
0x14000a2dc  lea     r9, [rbp+ReturnLength]; ReturnLength
0x14000a2e0  mov     r8d, r14d; SystemInformationLength
0x14000a2e3  mov     rdx, rbx; SystemInformation
0x14000a2e6  mov     ecx, 5; SystemInformationClass
0x14000a2eb  call    cs:__imp_NtQuerySystemInformation
0x14000a2f1  cmp     eax, 0C0000004h
0x14000a2f6  jnz     short loc_14000A321
0x14000a2f8  mov     rcx, rbx; lpMem
0x14000a2fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a300  mov     r14d, [rbp+ReturnLength]
0x14000a304  add     r14d, 8000h
0x14000a30b  mov     ecx, r14d; dwBytes
0x14000a30e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a313  mov     rbx, rax
0x14000a316  test    rax, rax
0x14000a319  jz      loc_14000A3BA
0x14000a31f  jmp     short loc_14000A2D7
0x14000a321  test    eax, eax
0x14000a323  js      short loc_14000A34C
0x14000a325  xor     r15d, r15d
0x14000a328  xor     r12d, r12d
0x14000a32b  mov     rax, cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x14000a332  mov     [rbp+var_20], rax
0x14000a336  mov     [rbp+var_18], r12
0x14000a33a  mov     cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA, rbx; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x14000a341  lea     rcx, [rbp+var_20]
0x14000a345  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x14000a34a  jmp     short loc_14000A2D7
0x14000a34c  mov     rcx, rbx; lpMem
0x14000a34f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a354  jmp     short loc_14000A3BA
0x14000a356  xor     ebx, ebx
0x14000a358  jmp     loc_14000A28A
0x14000a35d  mov     r9d, [rbx+60h]; Value
0x14000a361  mov     r8d, 2; CounterId
0x14000a367  mov     rdx, [rsi+220h]; Instance
0x14000a36e  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000a375  call    cs:__imp_PerfSetULongCounterValue
0x14000a37b  mov     r9d, [rbx+4]; Value
0x14000a37f  mov     r8d, 3; CounterId
0x14000a385  mov     rdx, [rsi+220h]; Instance
0x14000a38c  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000a393  call    cs:__imp_PerfSetULongCounterValue
0x14000a399  mov     r9, [rbx+0C8h]; Value
0x14000a3a0  mov     r8d, 4; CounterId
0x14000a3a6  mov     rdx, [rsi+220h]; Instance
0x14000a3ad  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000a3b4  call    cs:__imp_PerfSetULongLongCounterValue
0x14000a3ba  lea     rcx, ?s_ProcessDATALock@CInterceptor_IWbemSyncProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x14000a3c1  test    r12d, r12d
0x14000a3c4  jz      short loc_14000A3CE
0x14000a3c6  call    cs:__imp_ReleaseSRWLockShared
0x14000a3cc  jmp     short loc_14000A3D4
0x14000a3ce  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a3d4  mov     r9, rdi; Value
0x14000a3d7  mov     r8d, 0Bh; CounterId
0x14000a3dd  mov     rdx, [rsi+220h]; Instance
0x14000a3e4  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000a3eb  call    cs:__imp_PerfSetULongLongCounterValue
0x14000a3f1  xor     eax, eax
0x14000a3f3  lea     r11, [rsp+40h+var_s0]
0x14000a3f8  mov     rbx, [r11+30h]
0x14000a3fc  mov     rsi, [r11+48h]
0x14000a400  mov     rsp, r11
0x14000a403  pop     r15
0x14000a405  pop     r14
0x14000a407  pop     r12
0x14000a409  pop     rdi
0x14000a40a  pop     rbp
0x14000a40b  retn
```
