# CEventSystem2::CEventSystem2(ushort const *)

- ea: `0x180034588`
- end: `0x180034723`
- name: `??0CEventSystem2@@QEAA@PEBG@Z`
- size: `411`
- prototype: `CEventSystem2 *__fastcall(CEventSystem2 *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021b30`

## callees

- `0x180008938`
- `0x18000ad8c`
- `0x180034588`
- `0x180035080`
- `0x180035184`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003460c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003460c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800346f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800346f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800346b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800346b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034707`

## string_xrefs

- `0x180034656`: `com\complus\src\events\tier2\eventsystem2.cpp`
- `0x18003467e`: `com\complus\src\events\tier2\eventsystem2.cpp`

## pseudocode

```c
CEventSystem2 *__fastcall CEventSystem2::CEventSystem2(CEventSystem2 *this, const unsigned __int16 *a2)
{
  struct IEventDatabase **v2; // rsi
  int v5; // eax
  int v6; // eax
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  *((_DWORD *)this + 4) = 1;
  v2 = (struct IEventDatabase **)((char *)this + 24);
  *(_QWORD *)this = &CEventSystem2::`vftable'{for `IEventSystemTier2'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 1) = &CEventSystem2::`vftable'{for `IEventSystemTier2Inproc'};
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 18) = 10;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 17;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 17;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 10;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 40) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 3, 0x1F4u);
  Notifier::Notifier((CEventSystem2 *)((char *)this + 168), this);
  TransientSubChecker::CheckerThread::CheckerThread((CEventSystem2 *)((char *)this + 240), this);
  *((_DWORD *)this + 100) = 0;
  v5 = RegDatabase::Create(0, v2);
  if ( v5 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x66u, 0x11u, v5);
  v6 = (*(__int64 (__fastcall **)(struct IEventDatabase *, const unsigned __int16 *))(*(_QWORD *)*v2 + 32LL))(*v2, a2);
  if ( v6 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x69u, 0x11u, v6);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\EventSystem", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"ParallelFiringTimeoutEnabled", 0, 0, &g_dwParallelFiringTimeout, &cbData) )
      *(_DWORD *)&g_dwParallelFiringTimeout = 0;
    RegCloseKey(hKey);
  }
  return this;
}

```

## disassembly

```asm
0x180034588  mov     [rsp+arg_8], rbx
0x18003458d  mov     [rsp+arg_18], rbp
0x180034592  push    rsi
0x180034593  push    rdi
0x180034594  push    r14
0x180034596  sub     rsp, 30h
0x18003459a  mov     dword ptr [rcx+10h], 1
0x1800345a1  lea     rsi, [rcx+18h]
0x1800345a5  xor     r14d, r14d
0x1800345a8  lea     rax, ??_7CEventSystem2@@6BIEventSystemTier2@@@; const CEventSystem2::`vftable'{for `IEventSystemTier2'}
0x1800345af  mov     [rcx], rax
0x1800345b2  mov     rbp, rdx
0x1800345b5  mov     [rsi], r14
0x1800345b8  lea     rax, ??_7CEventSystem2@@6BIEventSystemTier2Inproc@@@; const CEventSystem2::`vftable'{for `IEventSystemTier2Inproc'}
0x1800345bf  mov     [rcx+8], rax
0x1800345c3  mov     rdi, rcx
0x1800345c6  mov     [rcx+20h], r14
0x1800345ca  lea     eax, [r14+0Ah]
0x1800345ce  mov     [rcx+48h], eax
0x1800345d1  mov     edx, 1F4h; dwSpinCount
0x1800345d6  mov     [rcx+28h], r14
0x1800345da  mov     qword ptr [rcx+30h], 11h
0x1800345e2  mov     [rcx+38h], r14
0x1800345e6  mov     [rcx+40h], r14
0x1800345ea  mov     [rcx+50h], r14
0x1800345ee  mov     qword ptr [rcx+58h], 11h
0x1800345f6  mov     [rcx+60h], r14
0x1800345fa  mov     [rcx+68h], r14
0x1800345fe  mov     [rcx+70h], eax
0x180034601  mov     [rcx+0A0h], r14d
0x180034608  add     rcx, 78h ; 'x'; lpCriticalSection
0x18003460c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180034612  lea     rcx, [rdi+0A8h]; this
0x180034619  mov     rdx, rdi; struct CEventSystem2 *
0x18003461c  mov     [rdi+0A0h], eax
0x180034622  call    ??0Notifier@@QEAA@AEAVCEventSystem2@@@Z; Notifier::Notifier(CEventSystem2 &)
0x180034627  lea     rcx, [rdi+0F0h]; this
0x18003462e  mov     rdx, rdi; struct CEventSystem2 *
0x180034631  call    ??0CheckerThread@TransientSubChecker@@QEAA@AEAVCEventSystem2@@@Z; TransientSubChecker::CheckerThread::CheckerThread(CEventSystem2 &)
0x180034636  mov     rdx, rsi; struct IEventDatabase **
0x180034639  mov     [rdi+190h], r14d
0x180034640  xor     ecx, ecx; unsigned __int16 *
0x180034642  call    ?Create@RegDatabase@@SAJPEBGAEAPEAUIEventDatabase@@@Z; RegDatabase::Create(ushort const *,IEventDatabase * &)
0x180034647  test    eax, eax
0x180034649  jns     short loc_180034662
0x18003464b  lea     r8d, [r14+11h]; unsigned __int16
0x18003464f  mov     r9d, eax; int
0x180034652  lea     edx, [r14+66h]; unsigned int
0x180034656  lea     rcx, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x18003465d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180034662  mov     rcx, [rsi]
0x180034665  mov     rdx, rbp
0x180034668  mov     rax, [rcx]
0x18003466b  mov     rax, [rax+20h]
0x18003466f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034674  test    eax, eax
0x180034676  jns     short loc_180034691
0x180034678  mov     r8d, 11h; unsigned __int16
0x18003467e  lea     rcx, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x180034685  mov     r9d, eax; int
0x180034688  lea     edx, [r8+58h]; unsigned int
0x18003468c  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180034691  lea     rax, [rsp+48h+hKey]
0x180034696  mov     [rsp+48h+hKey], r14
0x18003469b  mov     r9d, 20019h; samDesired
0x1800346a1  mov     [rsp+48h+phkResult], rax; phkResult
0x1800346a6  xor     r8d, r8d; ulOptions
0x1800346a9  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\EventSystem"
0x1800346b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800346b7  call    cs:__imp_RegOpenKeyExW
0x1800346bd  test    eax, eax
0x1800346bf  jnz     short loc_18003470D
0x1800346c1  mov     rcx, [rsp+48h+hKey]; hKey
0x1800346c6  lea     rax, [rsp+48h+cbData]
0x1800346cb  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800346d0  lea     rdx, aParallelfiring; "ParallelFiringTimeoutEnabled"
0x1800346d7  lea     rax, ?g_dwParallelFiringTimeout@@3KA; ulong g_dwParallelFiringTimeout
0x1800346de  mov     [rsp+48h+cbData], 4
0x1800346e6  xor     r9d, r9d; lpType
0x1800346e9  mov     [rsp+48h+phkResult], rax; lpData
0x1800346ee  xor     r8d, r8d; lpReserved
0x1800346f1  call    cs:__imp_RegQueryValueExW
0x1800346f7  test    eax, eax
0x1800346f9  jz      short loc_180034702
0x1800346fb  mov     cs:?g_dwParallelFiringTimeout@@3KA, r14d; ulong g_dwParallelFiringTimeout
0x180034702  mov     rcx, [rsp+48h+hKey]; hKey
0x180034707  call    cs:__imp_RegCloseKey
0x18003470d  mov     rbx, [rsp+48h+arg_8]
0x180034712  mov     rax, rdi
0x180034715  mov     rbp, [rsp+48h+arg_18]
0x18003471a  add     rsp, 30h
0x18003471e  pop     r14
0x180034720  pop     rdi
0x180034721  pop     rsi
0x180034722  retn
```
