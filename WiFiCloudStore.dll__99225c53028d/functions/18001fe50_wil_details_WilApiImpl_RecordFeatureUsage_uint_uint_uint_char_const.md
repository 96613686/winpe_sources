# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001fe50`
- end: `0x18002022f`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `991`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callees

- `0x18000e240`
- `0x18000e760`
- `0x18000f450`
- `0x18000f920`
- `0x18001fe50`
- `0x180028800`
- `0x180029b24`
- `0x18002d60c`
- `0x18002da18`
- `0x18002da4c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ff63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ff63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ff4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ff4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ffe1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020052`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020145`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ffe1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020052`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020145`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020031`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800200a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002021a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020031`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800200a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002021a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800200d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800200f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020112`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800200d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800200f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020112`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020104`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800200e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020104`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800201c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800201d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800201c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800201d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020196`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800201a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020206`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800201a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020206`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800201c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800201c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800201b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800201b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020181`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020181`

## string_xrefs

- `0x18001ff45`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // esi
  unsigned int v5; // edi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  PSRWLOCK v8; // rbx
  int v9; // eax
  char Ptr; // di
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  void *v15; // rbx
  HANDLE v16; // rax
  struct _TP_TIMER *v17; // rcx
  DWORD LastError; // esi
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v20; // rdi
  DWORD v21; // ebx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-F8h] BYREF
  _BYTE v23[48]; // [rsp+30h] [rbp-E8h] BYREF
  LPVOID v24; // [rsp+60h] [rbp-B8h]
  _BYTE v25[48]; // [rsp+70h] [rbp-A8h] BYREF
  LPVOID v26; // [rsp+A0h] [rbp-78h]
  _BYTE v27[48]; // [rsp+B0h] [rbp-68h] BYREF
  LPVOID lpMem; // [rsp+E0h] [rbp-38h]

  v4 = (unsigned int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( !(_DWORD)this && !a3 && !v5 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
      wil::details_abi::FeatureStateData::RecordUsage((wil::details_abi::FeatureStateData *)SRWLock);
    }
    return;
  }
  if ( (a2 & 0x40000000) != 0 )
  {
    wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
      &wil::details::g_featureStateManager,
      (unsigned int)this,
      a2,
      a3);
    return;
  }
  if ( !a3 && v5 != 254 )
  {
    pftDueTime.dwLowDateTime = (unsigned int)this;
    pftDueTime.dwHighDateTime = (unsigned __int16)a2;
    if ( a2 < 0 )
      HIWORD(pftDueTime.dwHighDateTime) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_19;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_19:
      ((void (__fastcall *)(struct _FILETIME *))ProcAddress)(&pftDueTime);
    return;
  }
  if ( !wil::details::g_featureStateManager
    || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    return;
  }
  v8 = SRWLock;
  if ( v5 == 254 )
  {
    wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v23);
    AcquireSRWLockExclusive(v8);
    if ( LOBYTE(v8[8].Ptr) )
      wil::details_abi::RawUsageIndex::Swap(
        (wil::details_abi::RawUsageIndex *)v23,
        (struct wil::details_abi::RawUsageIndex *)&v8[1]);
    if ( LOBYTE(v8[16].Ptr) )
      wil::details_abi::RawUsageIndex::Swap(
        (wil::details_abi::RawUsageIndex *)v25,
        (struct wil::details_abi::RawUsageIndex *)&v8[9]);
    if ( LOBYTE(v8[24].Ptr) )
      wil::details_abi::RawUsageIndex::Swap(
        (wil::details_abi::RawUsageIndex *)v27,
        (struct wil::details_abi::RawUsageIndex *)&v8[17]);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v23);
    v11 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
    v13 = v26;
    if ( v26 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
    }
    v15 = v24;
    if ( v24 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
    }
    goto LABEL_48;
  }
  if ( v5 <= 0xC7 || v5 - 256 <= 0xFF )
  {
    AcquireSRWLockExclusive(SRWLock);
    if ( v5 <= 7 && (v9 = 204, _bittest(&v9, v5)) || v5 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(&v8[1], v5, v4);
      Ptr = (char)v8[8].Ptr;
    }
    else
    {
      Ptr = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              &v8[9],
              v5,
              v4,
              a3);
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    if ( Ptr )
    {
LABEL_48:
      if ( !wil::details::g_processShutdownInProgress
        && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
      {
        AcquireSRWLockExclusive(&stru_1800528E8);
        if ( !byte_180052909 )
        {
          v17 = pti;
          if ( pti )
            goto LABEL_56;
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              &wil::details::g_featureStateManager,
                              0);
          v20 = pti;
          if ( pti )
          {
            v21 = GetLastError();
            SetThreadpoolTimer(v20, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v20, 1);
            CloseThreadpoolTimer(v20);
            SetLastError(v21);
          }
          pti = ThreadpoolTimer;
          SetLastError(LastError);
          v17 = pti;
          if ( pti )
          {
LABEL_56:
            pftDueTime = (struct _FILETIME)-3000000000LL;
            SetThreadpoolTimer(v17, &pftDueTime, 0, 0x124F8u);
            byte_180052909 = 1;
          }
        }
        ReleaseSRWLockExclusive(&stru_1800528E8);
      }
    }
  }
}

```

## disassembly

```asm
0x18001fe50  push    rbx
0x18001fe52  push    rbp
0x18001fe53  push    rsi
0x18001fe54  push    rdi
0x18001fe55  push    r14
0x18001fe57  sub     rsp, 0F0h
0x18001fe5e  mov     ebp, r8d
0x18001fe61  mov     esi, ecx
0x18001fe63  mov     edi, edx
0x18001fe65  btr     edi, 1Fh
0x18001fe69  test    ecx, ecx
0x18001fe6b  jnz     short loc_18001FED4
0x18001fe6d  test    r8d, r8d
0x18001fe70  jnz     short loc_18001FED4
0x18001fe72  test    edi, edi
0x18001fe74  jnz     short loc_18001FED4
0x18001fe76  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dil; bool wil::details::g_processShutdownInProgress
0x18001fe7d  jnz     loc_180020221
0x18001fe83  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001fe8a  test    rax, rax
0x18001fe8d  jz      short loc_18001FE9C
0x18001fe8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe94  test    al, al
0x18001fe96  jnz     loc_180020221
0x18001fe9c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001fea3  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001fea8  test    al, al
0x18001feaa  jz      loc_180020221
0x18001feb0  mov     rdx, cs:SRWLock; SRWLock
0x18001feb7  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001febe  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001fec3  mov     rcx, cs:SRWLock; this
0x18001feca  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001fecf  jmp     loc_180020221
0x18001fed4  bt      edi, 1Eh
0x18001fed8  jnb     short loc_18001FEFD
0x18001feda  movzx   r8d, di; unsigned __int16
0x18001fede  mov     r9d, ebp; unsigned int
0x18001fee1  mov     edx, esi; unsigned int
0x18001fee3  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001feea  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18001feef  add     rsp, 0F0h
0x18001fef6  pop     r14
0x18001fef8  pop     rdi
0x18001fef9  pop     rsi
0x18001fefa  pop     rbp
0x18001fefb  pop     rbx
0x18001fefc  retn
0x18001fefd  test    ebp, ebp
0x18001feff  jnz     loc_18001FF91
0x18001ff05  cmp     edi, 0FEh
0x18001ff0b  jz      loc_18001FF91
0x18001ff11  mov     qword ptr [rsp+118h+pftDueTime.dwLowDateTime], 0
0x18001ff1a  mov     [rsp+118h+pftDueTime.dwLowDateTime], esi
0x18001ff1e  mov     word ptr [rsp+118h+pftDueTime.dwHighDateTime], di
0x18001ff23  test    edx, edx
0x18001ff25  jns     short loc_18001FF2D
0x18001ff27  or      word ptr [rsp+118h+pftDueTime.dwHighDateTime+2], 1
0x18001ff2d  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001ff34  test    rax, rax
0x18001ff37  jnz     short loc_18001FF79
0x18001ff39  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ff40  test    rax, rax
0x18001ff43  jnz     short loc_18001FF59
0x18001ff45  lea     rcx, ModuleName; "ntdll.dll"
0x18001ff4c  call    cs:__imp_GetModuleHandleW
0x18001ff52  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ff59  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001ff60  mov     rcx, rax; hModule
0x18001ff63  call    cs:__imp_GetProcAddress
0x18001ff69  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001ff70  test    rax, rax
0x18001ff73  jz      loc_180020221
0x18001ff79  lea     rcx, [rsp+118h+pftDueTime]
0x18001ff7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff83  add     rsp, 0F0h
0x18001ff8a  pop     r14
0x18001ff8c  pop     rdi
0x18001ff8d  pop     rsi
0x18001ff8e  pop     rbp
0x18001ff8f  pop     rbx
0x18001ff90  retn
0x18001ff91  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001ff98  jz      loc_180020221
0x18001ff9e  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001ffa5  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001ffaa  test    al, al
0x18001ffac  jz      loc_180020221
0x18001ffb2  mov     rbx, cs:SRWLock
0x18001ffb9  cmp     edi, 0FEh
0x18001ffbf  jz      loc_180020045
0x18001ffc5  cmp     edi, 0C7h
0x18001ffcb  jbe     short loc_18001FFDE
0x18001ffcd  lea     eax, [rdi-100h]
0x18001ffd3  cmp     eax, 0FFh
0x18001ffd8  ja      loc_180020221
0x18001ffde  mov     rcx, rbx; SRWLock
0x18001ffe1  call    cs:__imp_AcquireSRWLockExclusive
0x18001ffe7  cmp     edi, 7
0x18001ffea  ja      short loc_18001FFF6
0x18001ffec  mov     eax, 0CCh
0x18001fff1  bt      eax, edi
0x18001fff4  jb      short loc_180020017
0x18001fff6  lea     eax, [rdi-100h]
0x18001fffc  cmp     eax, 7Fh
0x18001ffff  jbe     short loc_180020017
0x180020001  lea     rcx, [rbx+48h]
0x180020005  mov     r9d, ebp
0x180020008  mov     r8d, esi
0x18002000b  mov     edx, edi
0x18002000d  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020012  movzx   edi, al
0x180020015  jmp     short loc_180020029
0x180020017  mov     r8d, esi
0x18002001a  mov     edx, edi
0x18002001c  lea     rcx, [rbx+8]
0x180020020  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020025  movzx   edi, byte ptr [rbx+40h]
0x180020029  test    rbx, rbx
0x18002002c  jz      short loc_180020037
0x18002002e  mov     rcx, rbx; SRWLock
0x180020031  call    cs:__imp_ReleaseSRWLockExclusive
0x180020037  test    dil, dil
0x18002003a  jz      loc_180020221
0x180020040  jmp     loc_180020118
0x180020045  lea     rcx, [rsp+118h+var_E8]; this
0x18002004a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18002004f  mov     rcx, rbx; SRWLock
0x180020052  call    cs:__imp_AcquireSRWLockExclusive
0x180020058  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18002005c  cmp     byte ptr [rdx+38h], 0
0x180020060  jz      short loc_18002006C
0x180020062  lea     rcx, [rsp+118h+var_E8]; this
0x180020067  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18002006c  cmp     byte ptr [rbx+80h], 0
0x180020073  jz      short loc_180020083
0x180020075  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180020079  lea     rcx, [rsp+118h+var_A8]; this
0x18002007e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180020083  cmp     byte ptr [rbx+0C0h], 0
0x18002008a  jz      short loc_1800200A0
0x18002008c  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180020093  lea     rcx, [rsp+118h+var_68]; this
0x18002009b  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800200a0  test    rbx, rbx
0x1800200a3  jz      short loc_1800200AE
0x1800200a5  mov     rcx, rbx; SRWLock
0x1800200a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800200ae  lea     rcx, [rsp+118h+var_E8]; this
0x1800200b3  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800200b8  mov     rbx, [rsp+118h+lpMem]
0x1800200c0  test    rbx, rbx
0x1800200c3  jz      short loc_1800200D9
0x1800200c5  call    cs:__imp_GetProcessHeap
0x1800200cb  mov     rcx, rax; hHeap
0x1800200ce  mov     r8, rbx; lpMem
0x1800200d1  xor     edx, edx; dwFlags
0x1800200d3  call    cs:__imp_HeapFree
0x1800200d9  mov     rbx, [rsp+118h+var_78]
0x1800200e1  test    rbx, rbx
0x1800200e4  jz      short loc_1800200FA
0x1800200e6  call    cs:__imp_GetProcessHeap
0x1800200ec  mov     rcx, rax; hHeap
0x1800200ef  mov     r8, rbx; lpMem
0x1800200f2  xor     edx, edx; dwFlags
0x1800200f4  call    cs:__imp_HeapFree
0x1800200fa  mov     rbx, [rsp+118h+var_B8]
0x1800200ff  test    rbx, rbx
0x180020102  jz      short loc_180020118
0x180020104  call    cs:__imp_GetProcessHeap
0x18002010a  mov     rcx, rax; hHeap
0x18002010d  mov     r8, rbx; lpMem
0x180020110  xor     edx, edx; dwFlags
0x180020112  call    cs:__imp_HeapFree
0x180020118  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002011f  jnz     loc_180020221
0x180020125  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002012c  test    rax, rax
0x18002012f  jz      short loc_18002013E
0x180020131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020136  test    al, al
0x180020138  jnz     loc_180020221
0x18002013e  lea     rcx, stru_1800528E8; SRWLock
0x180020145  call    cs:__imp_AcquireSRWLockExclusive
0x18002014b  cmp     cs:byte_180052909, 0
0x180020152  jnz     loc_180020213
0x180020158  mov     rcx, qword ptr cs:pti
0x18002015f  test    rcx, rcx
0x180020162  jnz     loc_1800201E9
0x180020168  call    cs:__imp_GetLastError
0x18002016e  mov     esi, eax
0x180020170  xor     r8d, r8d; pcbe
0x180020173  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18002017a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020181  call    cs:__imp_CreateThreadpoolTimer
0x180020187  mov     rbp, rax
0x18002018a  mov     rdi, qword ptr cs:pti
0x180020191  test    rdi, rdi
0x180020194  jz      short loc_1800201CE
0x180020196  call    cs:__imp_GetLastError
0x18002019c  mov     ebx, eax
0x18002019e  xor     r9d, r9d; msWindowLength
0x1800201a1  xor     r8d, r8d; msPeriod
0x1800201a4  xor     edx, edx; pftDueTime
0x1800201a6  mov     rcx, rdi; pti
0x1800201a9  call    cs:__imp_SetThreadpoolTimer
0x1800201af  mov     edx, 1; fCancelPendingCallbacks
0x1800201b4  mov     rcx, rdi; pti
0x1800201b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800201bd  mov     rcx, rdi; pti
0x1800201c0  call    cs:__imp_CloseThreadpoolTimer
0x1800201c6  mov     ecx, ebx; dwErrCode
0x1800201c8  call    cs:__imp_SetLastError
0x1800201ce  mov     qword ptr cs:pti, rbp
0x1800201d5  mov     ecx, esi; dwErrCode
0x1800201d7  call    cs:__imp_SetLastError
0x1800201dd  mov     rcx, qword ptr cs:pti; pti
0x1800201e4  test    rcx, rcx
0x1800201e7  jz      short loc_180020213
0x1800201e9  mov     rax, 0FFFFFFFF4D2FA200h
0x1800201f3  mov     qword ptr [rsp+118h+pftDueTime.dwLowDateTime], rax
0x1800201f8  mov     r9d, 124F8h; msWindowLength
0x1800201fe  xor     r8d, r8d; msPeriod
0x180020201  lea     rdx, [rsp+118h+pftDueTime]; pftDueTime
0x180020206  call    cs:__imp_SetThreadpoolTimer
0x18002020c  mov     cs:byte_180052909, 1
0x180020213  lea     rcx, stru_1800528E8; SRWLock
0x18002021a  call    cs:__imp_ReleaseSRWLockExclusive
0x180020220  nop
0x180020221  add     rsp, 0F0h
0x180020228  pop     r14
0x18002022a  pop     rdi
0x18002022b  pop     rsi
0x18002022c  pop     rbp
0x18002022d  pop     rbx
0x18002022e  retn
```
