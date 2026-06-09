# CInterceptor_Batching_IWbemSyncObjectSink::Indicate(long,IWbemClassObject * *)

- ea: `0x1400092a0`
- end: `0x1400095d5`
- name: `?Indicate@CInterceptor_Batching_IWbemSyncObjectSink@@UEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(CInterceptor_Batching_IWbemSyncObjectSink *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400092a0`
- `0x140009860`
- `0x14000a0f0`
- `0x14000a414`
- `0x14000a530`
- `0x140027328`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140009548`
- `ntdll!NtQuerySystemInformation` at `0x140009548`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009457`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400093b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400093b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000947f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000947f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009515`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400093c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400093c8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x140009440`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x140009474`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x140009440`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x140009474`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x140009401`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000941f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x140009401`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000941f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000931d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000931d`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x1400094cf`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x1400094cf`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1400094ec`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1400094ec`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x1400094b5`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x1400094b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_Batching_IWbemSyncObjectSink::Indicate(
        CInterceptor_Batching_IWbemSyncObjectSink *this,
        int a2,
        struct IWbemClassObject **a3)
{
  __int64 v6; // rdi
  _FILETIME v8; // r13
  unsigned __int64 v9; // rcx
  ULONGLONG *v10; // rbx
  DWORD CurrentProcessId; // eax
  __int64 v12; // rcx
  ULONG v13; // r15d
  int v14; // r12d
  NTSTATUS v15; // eax
  _QWORD v16[11]; // [rsp+20h] [rbp-58h] BYREF
  ULONG ReturnLength; // [rsp+80h] [rbp+8h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+20h] BYREF

  v6 = *((_QWORD *)this + 31);
  if ( v6 )
  {
    if ( CInterceptor_IWbemSyncProvider::s_ConsoleDisplayState )
    {
      if ( *(_QWORD *)(v6 + 544) )
      {
        if ( *(_DWORD *)(v6 + 588) )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v8 = SystemTimeAsFileTime;
          if ( (unsigned __int64)qword_140060940 <= *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)(v6 + 560) )
          {
            SystemTimeAsFileTime.dwLowDateTime = 1;
            _InterlockedExchange64((volatile __int64 *)(v6 + 560), *(_QWORD *)&v8);
            CInterceptor_IWbemSyncProvider::RefreshCPURawData((CInterceptor_IWbemSyncProvider *)v6);
            ReturnLength = 0;
            v9 = CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp;
            if ( *(_QWORD *)&v8 - CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp > 0x11E1A300 )
            {
              qword_140060938 /= 0x2710uLL;
              Registry::Registry((Registry *)v16, L"Software\\Microsoft\\WBEM\\Tracing\\Providers", 3u);
              Registry::GetDWORD((Registry *)v16, L"ProcessDataInterval_ms", (unsigned int *)&qword_140060938);
              qword_140060938 *= 10000;
              Registry::~Registry((Registry *)v16);
              v9 = CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp;
            }
            if ( qword_140060938 >= *(_QWORD *)&v8 - v9 && CInterceptor_IWbemSyncProvider::s_pProcessDATA )
            {
              AcquireSRWLockShared(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
              v10 = (ULONGLONG *)CInterceptor_IWbemSyncProvider::s_pProcessDATA;
            }
            else
            {
              v13 = 1572864;
              _InterlockedExchange64(
                (volatile __int64 *)&CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp,
                *(_QWORD *)&v8);
              AcquireSRWLockExclusive(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
              v10 = (ULONGLONG *)operator new(0x180000u);
              v14 = 1;
              while ( v14 )
              {
                v15 = NtQuerySystemInformation(SystemProcessInformation, v10, v13, &ReturnLength);
                if ( v15 == -1073741820 )
                {
                  operator delete(v10);
                  v13 = ReturnLength + 0x8000;
                  v10 = (ULONGLONG *)operator new(ReturnLength + 0x8000);
                  if ( !v10 )
                    goto LABEL_19;
                }
                else
                {
                  if ( v15 < 0 )
                  {
                    operator delete(v10);
                    goto LABEL_19;
                  }
                  v14 = 0;
                  SystemTimeAsFileTime.dwLowDateTime = 0;
                  v16[0] = CInterceptor_IWbemSyncProvider::s_pProcessDATA;
                  v16[1] = 0;
                  CInterceptor_IWbemSyncProvider::s_pProcessDATA = v10;
                  CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>((__int64)v16);
                }
              }
            }
            if ( v10 )
            {
              CurrentProcessId = GetCurrentProcessId();
              while ( v10 )
              {
                if ( *((_DWORD *)v10 + 20) == CurrentProcessId )
                {
                  PerfSetULongCounterValue(
                    WmiprvSePerfCounter,
                    *(PPERF_COUNTERSET_INSTANCE *)(v6 + 544),
                    2u,
                    *((_DWORD *)v10 + 24));
                  PerfSetULongCounterValue(
                    WmiprvSePerfCounter,
                    *(PPERF_COUNTERSET_INSTANCE *)(v6 + 544),
                    3u,
                    *((_DWORD *)v10 + 1));
                  PerfSetULongLongCounterValue(
                    WmiprvSePerfCounter,
                    *(PPERF_COUNTERSET_INSTANCE *)(v6 + 544),
                    4u,
                    v10[25]);
                  break;
                }
                v12 = *(unsigned int *)v10;
                if ( (_DWORD)v12 )
                  v10 = (ULONGLONG *)((char *)v10 + v12);
                else
                  v10 = 0;
              }
            }
LABEL_19:
            if ( SystemTimeAsFileTime.dwLowDateTime )
              ReleaseSRWLockShared(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
            else
              ReleaseSRWLockExclusive(&CInterceptor_IWbemSyncProvider::s_ProcessDATALock);
            PerfSetULongLongCounterValue(
              WmiprvSePerfCounter,
              *(PPERF_COUNTERSET_INSTANCE *)(v6 + 544),
              0xBu,
              *(_QWORD *)&v8);
          }
        }
      }
    }
  }
  return CCommon_Batching_IWbemSyncObjectSink::Indicate(this, a2, a3);
}

```

## disassembly

```asm
0x1400092a0  mov     [rsp+arg_8], rbx
0x1400092a5  push    rbp
0x1400092a6  push    rsi
0x1400092a7  push    rdi
0x1400092a8  push    r12
0x1400092aa  push    r13
0x1400092ac  push    r14
0x1400092ae  push    r15
0x1400092b0  sub     rsp, 40h
0x1400092b4  mov     rbp, r8
0x1400092b7  mov     r14d, edx
0x1400092ba  mov     rsi, rcx
0x1400092bd  mov     rdi, [rcx+0F8h]
0x1400092c4  test    rdi, rdi
0x1400092c7  jz      short loc_1400092DC
0x1400092c9  cmp     cs:?s_ConsoleDisplayState@CInterceptor_IWbemSyncProvider@@0W4_MONITOR_DISPLAY_STATE@@A, 0; _MONITOR_DISPLAY_STATE CInterceptor_IWbemSyncProvider::s_ConsoleDisplayState
0x1400092d0  jz      short loc_1400092DC
0x1400092d2  cmp     qword ptr [rdi+220h], 0
0x1400092da  jnz     short loc_140009301
0x1400092dc  mov     r8, rbp; struct IWbemClassObject **
0x1400092df  mov     edx, r14d; int
0x1400092e2  mov     rcx, rsi; this
0x1400092e5  mov     rbx, [rsp+78h+arg_8]
0x1400092ed  add     rsp, 40h
0x1400092f1  pop     r15
0x1400092f3  pop     r14
0x1400092f5  pop     r13
0x1400092f7  pop     r12
0x1400092f9  pop     rdi
0x1400092fa  pop     rsi
0x1400092fb  pop     rbp
0x1400092fc  jmp     ?Indicate@CCommon_Batching_IWbemSyncObjectSink@@UEAAJJPEAPEAUIWbemClassObject@@@Z; CCommon_Batching_IWbemSyncObjectSink::Indicate(long,IWbemClassObject * *)
0x140009301  cmp     dword ptr [rdi+24Ch], 0
0x140009308  jz      short loc_1400092DC
0x14000930a  xor     r15d, r15d
0x14000930d  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], r15
0x140009315  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000931d  call    cs:__imp_GetSystemTimeAsFileTime
0x140009323  mov     r13d, [rsp+78h+SystemTimeAsFileTime.dwHighDateTime]
0x14000932b  shl     r13, 20h
0x14000932f  mov     eax, [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x140009336  or      r13, rax
0x140009339  mov     rax, r13
0x14000933c  sub     rax, [rdi+230h]
0x140009343  cmp     cs:qword_140060940, rax
0x14000934a  ja      short loc_1400092DC
0x14000934c  mov     [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 1
0x140009357  mov     rax, r13
0x14000935a  xchg    rax, [rdi+230h]
0x140009361  mov     rcx, rdi; this
0x140009364  call    ?RefreshCPURawData@CInterceptor_IWbemSyncProvider@@QEAAJXZ; CInterceptor_IWbemSyncProvider::RefreshCPURawData(void)
0x140009369  mov     [rsp+78h+ReturnLength], r15d
0x140009371  mov     rax, r13
0x140009374  mov     rcx, cs:?s_ulProcessDATATimestamp@CInterceptor_IWbemSyncProvider@@0_KA; unsigned __int64 CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp
0x14000937b  sub     rax, rcx
0x14000937e  cmp     rax, 11E1A300h
0x140009384  ja      loc_140009487
0x14000938a  mov     rax, r13
0x14000938d  sub     rax, rcx
0x140009390  cmp     cs:qword_140060938, rax
0x140009397  jb      loc_1400094FE
0x14000939d  cmp     cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA, 0; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x1400093a5  jz      loc_1400094FE
0x1400093ab  lea     rcx, ?s_ProcessDATALock@CInterceptor_IWbemSyncProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x1400093b2  call    cs:__imp_AcquireSRWLockShared
0x1400093b8  mov     rbx, cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x1400093bf  test    rbx, rbx
0x1400093c2  jz      loc_140009446
0x1400093c8  call    cs:__imp_GetCurrentProcessId
0x1400093ce  xchg    ax, ax
0x1400093d0  test    rbx, rbx
0x1400093d3  jz      short loc_140009446
0x1400093d5  cmp     [rbx+50h], eax
0x1400093d8  jz      short loc_1400093E9
0x1400093da  mov     ecx, [rbx]
0x1400093dc  test    ecx, ecx
0x1400093de  jnz     loc_1400095CD
0x1400093e4  mov     rbx, r15
0x1400093e7  jmp     short loc_1400093D0
0x1400093e9  mov     r9d, [rbx+60h]; Value
0x1400093ed  mov     r8d, 2; CounterId
0x1400093f3  mov     rdx, [rdi+220h]; Instance
0x1400093fa  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x140009401  call    cs:__imp_PerfSetULongCounterValue
0x140009407  mov     r9d, [rbx+4]; Value
0x14000940b  mov     r8d, 3; CounterId
0x140009411  mov     rdx, [rdi+220h]; Instance
0x140009418  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000941f  call    cs:__imp_PerfSetULongCounterValue
0x140009425  mov     r9, [rbx+0C8h]; Value
0x14000942c  mov     r8d, 4; CounterId
0x140009432  mov     rdx, [rdi+220h]; Instance
0x140009439  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x140009440  call    cs:__imp_PerfSetULongLongCounterValue
0x140009446  lea     rcx, ?s_ProcessDATALock@CInterceptor_IWbemSyncProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x14000944d  cmp     [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140009455  jz      short loc_14000947F
0x140009457  call    cs:__imp_ReleaseSRWLockShared
0x14000945d  mov     r9, r13; Value
0x140009460  mov     r8d, 0Bh; CounterId
0x140009466  mov     rdx, [rdi+220h]; Instance
0x14000946d  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x140009474  call    cs:__imp_PerfSetULongLongCounterValue
0x14000947a  jmp     loc_1400092DC
0x14000947f  call    cs:__imp_ReleaseSRWLockExclusive
0x140009485  jmp     short loc_14000945D
0x140009487  mov     rax, 346DC5D63886594Bh
0x140009491  mul     cs:qword_140060938
0x140009498  shr     rdx, 0Bh
0x14000949c  mov     cs:qword_140060938, rdx
0x1400094a3  mov     r8d, 3
0x1400094a9  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\Tracing\\Pro"...
0x1400094b0  lea     rcx, [rsp+78h+var_58]
0x1400094b5  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x1400094bb  nop
0x1400094bc  lea     r8, qword_140060938
0x1400094c3  lea     rdx, aProcessdataint; "ProcessDataInterval_ms"
0x1400094ca  lea     rcx, [rsp+78h+var_58]
0x1400094cf  call    cs:__imp_?GetDWORD@Registry@@QEAAHPEBGPEAK@Z; Registry::GetDWORD(ushort const *,ulong *)
0x1400094d5  imul    rax, cs:qword_140060938, 2710h
0x1400094e0  mov     cs:qword_140060938, rax
0x1400094e7  lea     rcx, [rsp+78h+var_58]
0x1400094ec  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x1400094f2  mov     rcx, cs:?s_ulProcessDATATimestamp@CInterceptor_IWbemSyncProvider@@0_KA; unsigned __int64 CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp
0x1400094f9  jmp     loc_14000938A
0x1400094fe  mov     r15d, 180000h
0x140009504  mov     rax, r13
0x140009507  xchg    rax, cs:?s_ulProcessDATATimestamp@CInterceptor_IWbemSyncProvider@@0_KA; unsigned __int64 CInterceptor_IWbemSyncProvider::s_ulProcessDATATimestamp
0x14000950e  lea     rcx, ?s_ProcessDATALock@CInterceptor_IWbemSyncProvider@@0U_RTL_SRWLOCK@@A; SRWLock
0x140009515  call    cs:__imp_AcquireSRWLockExclusive
0x14000951b  mov     ecx, r15d; dwBytes
0x14000951e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009523  mov     rbx, rax
0x140009526  mov     r12d, 1
0x14000952c  test    r12d, r12d
0x14000952f  jz      loc_1400095C5
0x140009535  lea     r9, [rsp+78h+ReturnLength]; ReturnLength
0x14000953d  mov     r8d, r15d; SystemInformationLength
0x140009540  mov     rdx, rbx; SystemInformation
0x140009543  mov     ecx, 5; SystemInformationClass
0x140009548  call    cs:__imp_NtQuerySystemInformation
0x14000954e  cmp     eax, 0C0000004h
0x140009553  jnz     short loc_140009582
0x140009555  mov     rcx, rbx; lpMem
0x140009558  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000955d  mov     r15d, [rsp+78h+ReturnLength]
0x140009565  add     r15d, 8000h
0x14000956c  mov     ecx, r15d; dwBytes
0x14000956f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009574  mov     rbx, rax
0x140009577  test    rax, rax
0x14000957a  jz      loc_140009446
0x140009580  jmp     short loc_14000952C
0x140009582  test    eax, eax
0x140009584  js      short loc_1400095B8
0x140009586  xor     r12d, r12d
0x140009589  mov     [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], r12d
0x140009591  mov     rax, cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x140009598  mov     [rsp+78h+var_58], rax
0x14000959d  mov     [rsp+78h+var_50], r12
0x1400095a2  mov     cs:?s_pProcessDATA@CInterceptor_IWbemSyncProvider@@0PEAU_SYSTEM_PROCESS_INFORMATION@@EA, rbx; _SYSTEM_PROCESS_INFORMATION * CInterceptor_IWbemSyncProvider::s_pProcessDATA
0x1400095a9  lea     rcx, [rsp+78h+var_58]
0x1400095ae  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x1400095b3  jmp     loc_14000952C
0x1400095b8  mov     rcx, rbx; lpMem
0x1400095bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400095c0  jmp     loc_140009446
0x1400095c5  xor     r15d, r15d
0x1400095c8  jmp     loc_1400093BF
0x1400095cd  add     rbx, rcx
0x1400095d0  jmp     loc_1400093D0
```
