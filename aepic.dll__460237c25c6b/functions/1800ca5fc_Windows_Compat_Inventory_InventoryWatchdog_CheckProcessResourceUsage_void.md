# Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)

- ea: `0x1800ca5fc`
- end: `0x1800ca8be`
- name: `?CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ`
- size: `706`
- prototype: `void __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cf9a0`

## callees

- `0x180005890`
- `0x180006938`
- `0x180008570`
- `0x1800295dc`
- `0x1800ca5fc`
- `0x1800cd230`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ca66a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ca82b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ca84d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ca66a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ca82b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ca84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ca697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ca697`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ca658`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ca658`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800ca6a7`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800ca6a7`

## string_xrefs

- `0x1800ca72d`: `Commit size [%zu] is greater than the max requested %zu for %d sec`
- `0x1800ca6c4`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x1800ca739`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`
- `0x1800ca7fa`: `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(RTL_SRWLOCK *this)
{
  char v2; // r13
  struct _FILETIME v3; // rbx
  PVOID Ptr; // r15
  float v5; // xmm7_4
  float v6; // xmm8_4
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  SIZE_T PagefileUsage; // rsi
  SIZE_T PeakPagefileUsage; // r12
  __int64 Ptr_high; // r8
  char v12; // r15
  __int64 v13; // rcx
  __int64 v14; // r8
  float ProcessCpuPercentage; // xmm0_4
  void (__fastcall *v16)(__int64, SIZE_T, __int64); // rax
  RTL_SRWLOCK *v17; // [rsp+50h] [rbp-91h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-89h] BYREF
  RTL_SRWLOCK *v19; // [rsp+60h] [rbp-81h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+68h] [rbp-79h] BYREF

  memset_0(&ppsmemCounters, 0, sizeof(ppsmemCounters));
  SystemTimeAsFileTime = 0;
  v2 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime;
  AcquireSRWLockExclusive(this + 3);
  Ptr = this[8].Ptr;
  v5 = *(float *)&this[12].Ptr;
  v6 = *((float *)&this[12].Ptr + 1);
  v17 = (RTL_SRWLOCK *)this[9].Ptr;
  v19 = this + 3;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  CurrentProcess = GetCurrentProcess();
  if ( K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u) )
  {
    PagefileUsage = ppsmemCounters.PagefileUsage;
    PeakPagefileUsage = ppsmemCounters.PeakPagefileUsage;
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage",
      520,
      "GetProcessMemoryInfo failed [%d]",
      LastError);
    PagefileUsage = 0;
    PeakPagefileUsage = 0;
  }
  this[10].Ptr = (char *)this[10].Ptr + PagefileUsage;
  if ( !Ptr
    || `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::alreadyAlertedCommitSizeBytes
    || PagefileUsage <= (unsigned __int64)Ptr )
  {
    `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::memExceededStart = 0;
  }
  else if ( `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::memExceededStart )
  {
    Ptr_high = HIDWORD(this[13].Ptr);
    if ( *(_QWORD *)&v3
       - `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::memExceededStart > (unsigned __int64)(10000000 * Ptr_high) )
    {
      `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::alreadyAlertedCommitSizeBytes = 1;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage",
        546,
        "Commit size [%zu] is greater than the max requested %zu for %d sec",
        PagefileUsage,
        (size_t)Ptr,
        Ptr_high);
      v12 = 1;
      goto LABEL_13;
    }
  }
  else
  {
    `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::memExceededStart = (__int64)v3;
  }
  v12 = 0;
LABEL_13:
  ProcessCpuPercentage = Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage();
  if ( ProcessCpuPercentage >= 0.0 )
    *(float *)&this[13].Ptr = ProcessCpuPercentage + *(float *)&this[13].Ptr;
  ++this[11].Ptr;
  if ( v5 <= 0.1
    || `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::alreadyAlertedCpuPercentage
    || ProcessCpuPercentage <= v5 )
  {
    `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::cpuExceededStart = 0;
  }
  else
  {
    v13 = `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::cpuExceededStart;
    if ( `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::cpuExceededStart )
    {
      v14 = HIDWORD(this[13].Ptr);
      if ( *(_QWORD *)&v3
         - `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::cpuExceededStart > (unsigned __int64)(10000000 * v14) )
      {
        `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::alreadyAlertedCpuPercentage = 1;
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage",
          578,
          "CPU percentage [%f] is greater than the max requested %f for %d sec",
          ProcessCpuPercentage,
          v5,
          v14);
        v2 = 1;
      }
    }
    else
    {
      `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage'::`2'::cpuExceededStart = (__int64)v3;
    }
  }
  if ( PeakPagefileUsage > (unsigned __int64)v17 )
  {
    AcquireSRWLockExclusive(this + 3);
    v17 = this + 3;
    this[9].Ptr = (PVOID)PeakPagefileUsage;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  }
  if ( ProcessCpuPercentage > v6 )
  {
    AcquireSRWLockExclusive(this + 3);
    *((float *)&this[12].Ptr + 1) = ProcessCpuPercentage;
    v17 = this + 3;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  }
  if ( v2 || v12 )
  {
    v16 = (void (__fastcall *)(__int64, SIZE_T, __int64))this[2].Ptr;
    if ( v16 )
    {
      LOBYTE(v14) = v2;
      LOBYTE(v13) = v12;
      v16(v13, PagefileUsage, v14);
    }
  }
}

```

## disassembly

```asm
0x1800ca5fc  mov     rax, rsp
0x1800ca5ff  push    rbp
0x1800ca600  push    rbx
0x1800ca601  push    rsi
0x1800ca602  push    rdi
0x1800ca603  push    r12
0x1800ca605  push    r13
0x1800ca607  push    r14
0x1800ca609  push    r15
0x1800ca60b  lea     rbp, [rax-5Fh]
0x1800ca60f  sub     rsp, 0F8h
0x1800ca616  movaps  xmmword ptr [rax-58h], xmm6
0x1800ca61a  movaps  xmmword ptr [rax-68h], xmm7
0x1800ca61e  movaps  xmmword ptr [rax-78h], xmm8
0x1800ca623  mov     rax, cs:__security_cookie
0x1800ca62a  xor     rax, rsp
0x1800ca62d  mov     [rbp+57h+var_80], rax
0x1800ca631  mov     rdi, rcx
0x1800ca634  mov     esi, 48h ; 'H'
0x1800ca639  mov     r8d, esi; Size
0x1800ca63c  lea     rcx, [rbp+57h+ppsmemCounters]; void *
0x1800ca640  xor     edx, edx; Val
0x1800ca642  call    memset_0
0x1800ca647  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ca64c  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800ca655  xor     r13b, r13b
0x1800ca658  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ca65e  mov     rbx, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ca663  lea     r14, [rdi+18h]
0x1800ca667  mov     rcx, r14; SRWLock
0x1800ca66a  call    cs:__imp_AcquireSRWLockExclusive
0x1800ca670  mov     rax, [rdi+48h]
0x1800ca674  lea     rcx, [rsp+130h+var_D8]
0x1800ca679  mov     r15, [rdi+40h]
0x1800ca67d  movss   xmm7, dword ptr [rdi+60h]
0x1800ca682  movss   xmm8, dword ptr [rdi+64h]
0x1800ca688  mov     [rsp+130h+var_E8], rax
0x1800ca68d  mov     [rsp+130h+var_D8], r14
0x1800ca692  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ca697  call    cs:__imp_GetCurrentProcess
0x1800ca69d  mov     r8d, esi; cb
0x1800ca6a0  lea     rdx, [rbp+57h+ppsmemCounters]; ppsmemCounters
0x1800ca6a4  mov     rcx, rax; Process
0x1800ca6a7  call    cs:__imp_K32GetProcessMemoryInfo
0x1800ca6ad  test    eax, eax
0x1800ca6af  jnz     short loc_1800CA6DE
0x1800ca6b1  call    cs:__imp_GetLastError
0x1800ca6b7  lea     r9, aGetprocessmemo; "GetProcessMemoryInfo failed [%d]"
0x1800ca6be  mov     r8d, 208h
0x1800ca6c4  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::InventoryWa"...
0x1800ca6cb  mov     dword ptr [rsp+130h+var_110], eax
0x1800ca6cf  lea     ecx, [rsi-47h]
0x1800ca6d2  call    AslLogCallPrintf
0x1800ca6d7  xor     esi, esi
0x1800ca6d9  xor     r12d, r12d
0x1800ca6dc  jmp     short loc_1800CA6E6
0x1800ca6de  mov     rsi, [rbp+57h+ppsmemCounters.PagefileUsage]
0x1800ca6e2  mov     r12, [rbp+57h+ppsmemCounters.PeakPagefileUsage]
0x1800ca6e6  add     [rdi+50h], rsi
0x1800ca6ea  test    r15, r15
0x1800ca6ed  jz      short loc_1800CA761
0x1800ca6ef  cmp     cs:?alreadyAlertedCommitSizeBytes@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_NA, r13b; bool `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::alreadyAlertedCommitSizeBytes
0x1800ca6f6  jnz     short loc_1800CA761
0x1800ca6f8  cmp     rsi, r15
0x1800ca6fb  jbe     short loc_1800CA761
0x1800ca6fd  mov     rdx, cs:?memExceededStart@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_KA; unsigned __int64 `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::memExceededStart
0x1800ca704  test    rdx, rdx
0x1800ca707  jnz     short loc_1800CA712
0x1800ca709  mov     cs:?memExceededStart@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_KA, rbx; unsigned __int64 `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::memExceededStart
0x1800ca710  jmp     short loc_1800CA76C
0x1800ca712  mov     r8d, [rdi+6Ch]
0x1800ca716  mov     rax, rbx
0x1800ca719  imul    rcx, r8, 989680h
0x1800ca720  sub     rax, rdx
0x1800ca723  cmp     rax, rcx
0x1800ca726  jbe     short loc_1800CA76C
0x1800ca728  mov     [rsp+130h+var_100], r8d
0x1800ca72d  lea     r9, aCommitSizeZuIs; "Commit size [%zu] is greater than the m"...
0x1800ca734  mov     qword ptr [rsp+130h+var_108], r15
0x1800ca739  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::InventoryWa"...
0x1800ca740  mov     r8d, 222h
0x1800ca746  mov     [rsp+130h+var_110], rsi
0x1800ca74b  mov     ecx, 1
0x1800ca750  mov     cs:?alreadyAlertedCommitSizeBytes@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_NA, 1; bool `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::alreadyAlertedCommitSizeBytes
0x1800ca757  call    AslLogCallPrintf
0x1800ca75c  mov     r15b, 1
0x1800ca75f  jmp     short loc_1800CA76F
0x1800ca761  mov     cs:?memExceededStart@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_KA, 0; unsigned __int64 `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::memExceededStart
0x1800ca76c  mov     r15b, r13b
0x1800ca76f  call    ?GetProcessCpuPercentage@InventoryWatchdog@Inventory@Compat@Windows@@CAMXZ; Windows::Compat::Inventory::InventoryWatchdog::GetProcessCpuPercentage(void)
0x1800ca774  movaps  xmm6, xmm0
0x1800ca777  comiss  xmm6, cs:__real@00000000
0x1800ca77e  jb      short loc_1800CA78D
0x1800ca780  movaps  xmm1, xmm0
0x1800ca783  addss   xmm1, dword ptr [rdi+68h]
0x1800ca788  movss   dword ptr [rdi+68h], xmm1
0x1800ca78d  inc     qword ptr [rdi+58h]
0x1800ca791  cvtps2pd xmm1, xmm7
0x1800ca794  comisd  xmm1, cs:__real@3fb999999999999a
0x1800ca79c  jbe     short loc_1800CA816
0x1800ca79e  cmp     cs:?alreadyAlertedCpuPercentage@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_NA, r13b; bool `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::alreadyAlertedCpuPercentage
0x1800ca7a5  jnz     short loc_1800CA816
0x1800ca7a7  comiss  xmm6, xmm7
0x1800ca7aa  jbe     short loc_1800CA816
0x1800ca7ac  mov     rcx, cs:?cpuExceededStart@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_KA; unsigned __int64 `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::cpuExceededStart
0x1800ca7b3  test    rcx, rcx
0x1800ca7b6  jnz     short loc_1800CA7C1
0x1800ca7b8  mov     cs:?cpuExceededStart@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_KA, rbx; unsigned __int64 `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::cpuExceededStart
0x1800ca7bf  jmp     short loc_1800CA821
0x1800ca7c1  mov     r8d, [rdi+6Ch]
0x1800ca7c5  sub     rbx, rcx
0x1800ca7c8  imul    rax, r8, 989680h
0x1800ca7cf  cmp     rbx, rax
0x1800ca7d2  jbe     short loc_1800CA821
0x1800ca7d4  mov     [rsp+130h+var_100], r8d
0x1800ca7d9  lea     r9, aCpuPercentageF; "CPU percentage [%f] is greater than the"...
0x1800ca7e0  xorps   xmm0, xmm0
0x1800ca7e3  movsd   qword ptr [rsp+130h+var_108], xmm1
0x1800ca7e9  cvtss2sd xmm0, xmm6
0x1800ca7ed  mov     r8d, 242h
0x1800ca7f3  mov     cs:?alreadyAlertedCpuPercentage@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_NA, 1; bool `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::alreadyAlertedCpuPercentage
0x1800ca7fa  lea     rdx, aWindowsCompatI_6; "Windows::Compat::Inventory::InventoryWa"...
0x1800ca801  mov     ecx, 1
0x1800ca806  movsd   [rsp+130h+var_110], xmm0
0x1800ca80c  call    AslLogCallPrintf
0x1800ca811  mov     r13b, 1
0x1800ca814  jmp     short loc_1800CA821
0x1800ca816  mov     cs:?cpuExceededStart@?1??CheckProcessResourceUsage@InventoryWatchdog@Inventory@Compat@Windows@@AEAAXXZ@4_KA, 0; unsigned __int64 `Windows::Compat::Inventory::InventoryWatchdog::CheckProcessResourceUsage(void)'::`2'::cpuExceededStart
0x1800ca821  cmp     r12, [rsp+130h+var_E8]
0x1800ca826  jbe     short loc_1800CA844
0x1800ca828  mov     rcx, r14; SRWLock
0x1800ca82b  call    cs:__imp_AcquireSRWLockExclusive
0x1800ca831  lea     rcx, [rsp+130h+var_E8]
0x1800ca836  mov     [rsp+130h+var_E8], r14
0x1800ca83b  mov     [rdi+48h], r12
0x1800ca83f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ca844  comiss  xmm6, xmm8
0x1800ca848  jbe     short loc_1800CA867
0x1800ca84a  mov     rcx, r14; SRWLock
0x1800ca84d  call    cs:__imp_AcquireSRWLockExclusive
0x1800ca853  lea     rcx, [rsp+130h+var_E8]
0x1800ca858  movss   dword ptr [rdi+64h], xmm6
0x1800ca85d  mov     [rsp+130h+var_E8], r14
0x1800ca862  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ca867  test    r13b, r13b
0x1800ca86a  jnz     short loc_1800CA871
0x1800ca86c  test    r15b, r15b
0x1800ca86f  jz      short loc_1800CA88B
0x1800ca871  mov     rax, [rdi+10h]
0x1800ca875  test    rax, rax
0x1800ca878  jz      short loc_1800CA88B
0x1800ca87a  movaps  xmm3, xmm6
0x1800ca87d  mov     r8b, r13b
0x1800ca880  mov     rdx, rsi
0x1800ca883  mov     cl, r15b
0x1800ca886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca88b  mov     rcx, [rbp+57h+var_80]
0x1800ca88f  xor     rcx, rsp; StackCookie
0x1800ca892  call    __security_check_cookie
0x1800ca897  lea     r11, [rsp+130h+var_38]
0x1800ca89f  movaps  xmm6, xmmword ptr [r11-18h]
0x1800ca8a4  movaps  xmm7, xmmword ptr [r11-28h]
0x1800ca8a9  movaps  xmm8, xmmword ptr [r11-38h]
0x1800ca8ae  mov     rsp, r11
0x1800ca8b1  pop     r15
0x1800ca8b3  pop     r14
0x1800ca8b5  pop     r13
0x1800ca8b7  pop     r12
0x1800ca8b9  pop     rdi
0x1800ca8ba  pop     rsi
0x1800ca8bb  pop     rbx
0x1800ca8bc  pop     rbp
0x1800ca8bd  retn
```
