# Locks_Initialize

- ea: `0x1800078cc`
- end: `0x1800079ff`
- name: `Locks_Initialize`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007314`

## callees

- `0x1800078cc`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800078e3`
- `KERNEL32!Sleep` at `0x1800078e3`
- `KERNEL32!GetProcAddress` at `0x180007923`
- `KERNEL32!GetProcAddress` at `0x18000793a`
- `KERNEL32!GetProcAddress` at `0x180007951`
- `KERNEL32!GetProcAddress` at `0x180007923`
- `KERNEL32!GetProcAddress` at `0x18000793a`
- `KERNEL32!GetProcAddress` at `0x180007951`
- `KERNEL32!GetModuleHandleW` at `0x18000790b`
- `KERNEL32!GetModuleHandleW` at `0x18000790b`
- `KERNEL32!GetSystemInfo` at `0x1800079cb`
- `KERNEL32!GetSystemInfo` at `0x1800079cb`

## string_xrefs

- `0x180007904`: `kernel32.dll`
- `0x180007919`: `SwitchToThread`

## pseudocode

```c
__int64 Locks_Initialize()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  unsigned int (*ProcAddress)(struct _RTL_CRITICAL_SECTION *, unsigned int); // rax
  DWORD dwNumberOfProcessors; // eax
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-38h] BYREF

  if ( !g_fLocksInitialized )
  {
    while ( _InterlockedExchange((volatile __int32 *)&g_lckInit, 1) )
      Sleep(0);
    if ( !g_fLocksInitialized )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      v1 = ModuleHandleW;
      if ( ModuleHandleW )
      {
        g_pfnSwitchToThread = (int (*)(void))GetProcAddress(ModuleHandleW, "SwitchToThread");
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))GetProcAddress(v1, "TryEnterCriticalSection");
        ProcAddress = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))GetProcAddress(
                                                                                        v1,
                                                                                        "SetCriticalSectionSpinCount");
        g_pfnSetCSSpinCount = ProcAddress;
      }
      else
      {
        ProcAddress = g_pfnSetCSSpinCount;
      }
      if ( !g_pfnSwitchToThread )
        g_pfnSwitchToThread = (int (*)(void))CFDListener::OnError;
      if ( !g_pfnTryEnterCritSec )
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))CFDListener::OnError;
      if ( !ProcAddress )
        g_pfnSetCSSpinCount = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))CFDListener::OnError;
      dwNumberOfProcessors = `NumProcessors'::`2'::s_nCPUs;
      if ( !`NumProcessors'::`2'::s_nCPUs )
      {
        memset(&SystemInfo, 0, sizeof(SystemInfo));
        GetSystemInfo(&SystemInfo);
        dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
        `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
      }
      g_cProcessors = dwNumberOfProcessors;
      _InterlockedExchange(&g_fLocksInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&g_lckInit, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x1800078cc  push    rbx
0x1800078ce  sub     rsp, 50h
0x1800078d2  cmp     cs:?g_fLocksInitialized@@3HA, 0; int g_fLocksInitialized
0x1800078d9  jnz     loc_1800079F4
0x1800078df  jmp     short loc_1800078E9
0x1800078e1  xor     ecx, ecx; dwMilliseconds
0x1800078e3  call    cs:__imp_Sleep
0x1800078e9  mov     eax, 1
0x1800078ee  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x1800078f4  test    eax, eax
0x1800078f6  jnz     short loc_1800078E1
0x1800078f8  cmp     cs:?g_fLocksInitialized@@3HA, eax; int g_fLocksInitialized
0x1800078fe  jnz     loc_1800079EC
0x180007904  lea     rcx, ModuleName; "kernel32.dll"
0x18000790b  call    cs:__imp_GetModuleHandleW
0x180007911  mov     rbx, rax
0x180007914  test    rax, rax
0x180007917  jz      short loc_180007960
0x180007919  lea     rdx, ProcName; "SwitchToThread"
0x180007920  mov     rcx, rax; hModule
0x180007923  call    cs:__imp_GetProcAddress
0x180007929  lea     rdx, aTryentercritic; "TryEnterCriticalSection"
0x180007930  mov     rcx, rbx; hModule
0x180007933  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rax; int (*g_pfnSwitchToThread)(void)
0x18000793a  call    cs:__imp_GetProcAddress
0x180007940  lea     rdx, aSetcriticalsec; "SetCriticalSectionSpinCount"
0x180007947  mov     rcx, rbx; hModule
0x18000794a  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rax; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180007951  call    cs:__imp_GetProcAddress
0x180007957  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000795e  jmp     short loc_180007967
0x180007960  mov     rax, cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180007967  cmp     cs:?g_pfnSwitchToThread@@3P6AHXZEA, 0; int (*g_pfnSwitchToThread)(void)
0x18000796f  jnz     short loc_18000797F
0x180007971  lea     rcx, ?OnError@CFDListener@@UEAAJJ_KPEBG@Z; CFDListener::OnError(long,unsigned __int64,ushort const *)
0x180007978  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rcx; int (*g_pfnSwitchToThread)(void)
0x18000797f  cmp     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, 0; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180007987  jnz     short loc_180007997
0x180007989  lea     rcx, ?OnError@CFDListener@@UEAAJJ_KPEBG@Z; CFDListener::OnError(long,unsigned __int64,ushort const *)
0x180007990  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rcx; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180007997  test    rax, rax
0x18000799a  jnz     short loc_1800079AA
0x18000799c  lea     rax, ?OnError@CFDListener@@UEAAJJ_KPEBG@Z; CFDListener::OnError(long,unsigned __int64,ushort const *)
0x1800079a3  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x1800079aa  mov     eax, cs:?s_nCPUs@?1??NumProcessors@@9@4HA; int `NumProcessors'::`2'::s_nCPUs
0x1800079b0  test    eax, eax
0x1800079b2  jnz     short loc_1800079DB
0x1800079b4  xorps   xmm0, xmm0
0x1800079b7  lea     rcx, [rsp+58h+SystemInfo]; lpSystemInfo
0x1800079bc  movups  xmmword ptr [rsp+58h+SystemInfo], xmm0
0x1800079c1  movups  xmmword ptr [rsp+58h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800079c6  movups  xmmword ptr [rsp+58h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800079cb  call    cs:__imp_GetSystemInfo
0x1800079d1  mov     eax, [rsp+58h+SystemInfo.dwNumberOfProcessors]
0x1800079d5  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x1800079db  mov     ecx, 1
0x1800079e0  mov     cs:?g_cProcessors@@3KA, eax; ulong g_cProcessors
0x1800079e6  xchg    ecx, cs:?g_fLocksInitialized@@3HA; int g_fLocksInitialized
0x1800079ec  xor     ecx, ecx
0x1800079ee  xchg    ecx, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x1800079f4  mov     eax, 1
0x1800079f9  add     rsp, 50h
0x1800079fd  pop     rbx
0x1800079fe  retn
```
