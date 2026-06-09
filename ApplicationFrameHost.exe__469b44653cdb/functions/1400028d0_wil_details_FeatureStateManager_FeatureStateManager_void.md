# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400028d0`
- end: `0x140002a0e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `318`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000a5c0`

## callees

- `0x1400028d0`
- `0x140005770`
- `0x140007f08`
- `0x1400090d0`
- `0x140009f8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002991`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400029d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002991`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400029d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000294c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400029c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000294c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002984`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400029c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000293e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400029bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000293e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400029bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400028e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000290f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400028e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000290f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // edi
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // edi
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rcx
  struct _TP_TIMER *v15; // rcx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( *((_QWORD *)this + 18) )
    wil_details_RtlUnregisterFeatureConfigurationChangeNotification();
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v14);
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v15);
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x1400028d0  push    rbx
0x1400028d2  push    rbp
0x1400028d3  push    rsi
0x1400028d4  push    rdi
0x1400028d5  sub     rsp, 28h
0x1400028d9  mov     rbx, rcx
0x1400028dc  mov     byte ptr [rcx], 0
0x1400028df  mov     rsi, [rcx+30h]
0x1400028e3  test    rsi, rsi
0x1400028e6  jz      short loc_140002900
0x1400028e8  call    cs:__imp_GetLastError
0x1400028ee  mov     edi, eax
0x1400028f0  mov     rcx, rsi; pti
0x1400028f3  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400028f8  mov     ecx, edi; dwErrCode
0x1400028fa  call    cs:__imp_SetLastError
0x140002900  xor     ebp, ebp
0x140002902  mov     [rbx+30h], rbp
0x140002906  mov     rsi, [rbx+38h]
0x14000290a  test    rsi, rsi
0x14000290d  jz      short loc_140002927
0x14000290f  call    cs:__imp_GetLastError
0x140002915  mov     edi, eax
0x140002917  mov     rcx, rsi; pti
0x14000291a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000291f  mov     ecx, edi; dwErrCode
0x140002921  call    cs:__imp_SetLastError
0x140002927  mov     [rbx+38h], rbp
0x14000292b  mov     rdi, [rbx+100h]
0x140002932  mov     [rbx+100h], rbp
0x140002939  test    rdi, rdi
0x14000293c  jz      short loc_140002952
0x14000293e  call    cs:__imp_GetProcessHeap
0x140002944  mov     rcx, rax; hHeap
0x140002947  mov     r8, rdi; lpMem
0x14000294a  xor     edx, edx; dwFlags
0x14000294c  call    cs:__imp_HeapFree
0x140002952  mov     rcx, [rbx+0E0h]; this
0x140002959  test    rcx, rcx
0x14000295c  jz      short loc_140002963
0x14000295e  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140002963  mov     rsi, [rbx+0D8h]
0x14000296a  mov     [rbx+0D8h], rbp
0x140002971  test    rsi, rsi
0x140002974  jz      short loc_14000298A
0x140002976  call    cs:__imp_GetProcessHeap
0x14000297c  mov     rcx, rax; hHeap
0x14000297f  mov     r8, rsi; lpMem
0x140002982  xor     edx, edx; dwFlags
0x140002984  call    cs:__imp_HeapFree
0x14000298a  lea     rcx, [rbx+98h]; lpCriticalSection
0x140002991  call    cs:__imp_DeleteCriticalSection
0x140002997  mov     rcx, [rbx+90h]
0x14000299e  test    rcx, rcx
0x1400029a1  jz      short loc_1400029A8
0x1400029a3  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x1400029a8  mov     rsi, [rbx+88h]
0x1400029af  mov     [rbx+88h], rbp
0x1400029b6  test    rsi, rsi
0x1400029b9  jz      short loc_1400029CF
0x1400029bb  call    cs:__imp_GetProcessHeap
0x1400029c1  mov     rcx, rax; hHeap
0x1400029c4  mov     r8, rsi; lpMem
0x1400029c7  xor     edx, edx; dwFlags
0x1400029c9  call    cs:__imp_HeapFree
0x1400029cf  lea     rcx, [rbx+48h]; lpCriticalSection
0x1400029d3  call    cs:__imp_DeleteCriticalSection
0x1400029d9  mov     rcx, [rbx+38h]; pti
0x1400029dd  test    rcx, rcx
0x1400029e0  jz      short loc_1400029E7
0x1400029e2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400029e7  mov     rcx, [rbx+30h]; pti
0x1400029eb  test    rcx, rcx
0x1400029ee  jz      short loc_1400029F6
0x1400029f0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400029f5  nop
0x1400029f6  mov     rcx, [rbx+10h]; lpMem
0x1400029fa  test    rcx, rcx
0x1400029fd  jz      short loc_140002A05
0x1400029ff  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140002a04  nop
0x140002a05  add     rsp, 28h
0x140002a09  pop     rdi
0x140002a0a  pop     rsi
0x140002a0b  pop     rbp
0x140002a0c  pop     rbx
0x140002a0d  retn
```
