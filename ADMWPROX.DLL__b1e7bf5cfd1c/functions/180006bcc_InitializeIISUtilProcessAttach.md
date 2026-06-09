# InitializeIISUtilProcessAttach

- ea: `0x180006bcc`
- end: `0x180006df7`
- name: `InitializeIISUtilProcessAttach`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002400`

## callees

- `0x180006bcc`
- `0x180006e00`
- `0x180007234`
- `0x180007324`
- `0x180007a54`
- `0x180007c70`
- `0x180007f1c`
- `0x180008064`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180006d21`
- `KERNEL32!GetSystemInfo` at `0x180006d21`
- `KERNEL32!GetModuleHandleW` at `0x180006c62`
- `KERNEL32!GetModuleHandleW` at `0x180006c62`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180006d57`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180006d7b`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180006d57`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180006d7b`
- `KERNEL32!Sleep` at `0x180006c3d`
- `KERNEL32!Sleep` at `0x180006c3d`
- `KERNEL32!GetProcAddress` at `0x180006c7a`
- `KERNEL32!GetProcAddress` at `0x180006c91`
- `KERNEL32!GetProcAddress` at `0x180006ca8`
- `KERNEL32!GetProcAddress` at `0x180006c7a`
- `KERNEL32!GetProcAddress` at `0x180006c91`
- `KERNEL32!GetProcAddress` at `0x180006ca8`

## string_xrefs

- `0x180006c1b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`
- `0x180006bdb`: `System\CurrentControlSet\Services\W3SVC\Parameters\IisUtil`
- `0x180006c5b`: `kernel32.dll`
- `0x180006c70`: `SwitchToThread`

## pseudocode

```c
__int64 InitializeIISUtilProcessAttach()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  unsigned int (*ProcAddress)(struct _RTL_CRITICAL_SECTION *, unsigned int); // rax
  char v4; // [rsp+28h] [rbp-40h]
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF

  g_dwDebugFlagsIISUtil = PuLoadDebugFlagsFromRegStr(
                            "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\IisUtil",
                            8u);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0x92u,
      "InitializeIISUtilProcessAttach",
      "InitializeIISUtilProcessAttach\n",
      v4);
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
        g_pfnSwitchToThread = (int (*)(void))FakeTryEnterCriticalSection;
      if ( !g_pfnTryEnterCritSec )
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))FakeTryEnterCriticalSection;
      if ( !ProcAddress )
        g_pfnSetCSSpinCount = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))FakeTryEnterCriticalSection;
      if ( !`NumProcessors'::`2'::s_nCPUs )
      {
        memset(&SystemInfo, 0, sizeof(SystemInfo));
        GetSystemInfo(&SystemInfo);
        `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
      }
      _InterlockedExchange(&g_fLocksInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&g_lckInit, 0);
  }
  dword_180010134 = 2;
  if ( InitializeCriticalSectionAndSpinCount(&CriticalSection, 0x80000000)
    && (dword_180010134 = 3, InitializeCriticalSectionAndSpinCount(&g_csTimerWrap, 0x800003E8))
    && (g_fInitCsTimerWrap = 1, dword_180010134 = 5, (unsigned int)ALLOC_CACHE_HANDLER::Initialize())
    && (dword_180010134 = 6, (unsigned __int8)LKRHashTableInit())
    && (dword_180010134 = 7, (int)BIG_REF_TRACE::InitializeStatic() >= 0)
    && (dword_180010134 = 8, (int)EVENT_LOG::Initialize() >= 0) )
  {
    dword_180010134 = 9;
    return 1;
  }
  else
  {
    TerminateIISUtilProcessDetach();
    return 0;
  }
}

```

## disassembly

```asm
0x180006bcc  mov     [rsp+arg_0], rbx
0x180006bd1  push    rsi
0x180006bd2  sub     rsp, 60h
0x180006bd6  mov     edx, 8
0x180006bdb  lea     rcx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x180006be2  call    PuLoadDebugFlagsFromRegStr
0x180006be7  test    al, 3
0x180006be9  mov     cs:g_dwDebugFlagsIISUtil, eax
0x180006bef  setnz   cl
0x180006bf2  test    al, 4
0x180006bf4  setnz   al
0x180006bf7  test    al, cl
0x180006bf9  jz      short loc_180006C27
0x180006bfb  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006c02  lea     rax, aInitializeiisu_0; "InitializeIISUtilProcessAttach\n"
0x180006c09  lea     r9, aInitializeiisu; "InitializeIISUtilProcessAttach"
0x180006c10  mov     [rsp+68h+var_48], rax; char *
0x180006c15  mov     r8d, 92h; unsigned int
0x180006c1b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006c22  call    PuDbgPrint
0x180006c27  cmp     cs:?g_fLocksInitialized@@3HA, 0; int g_fLocksInitialized
0x180006c2e  mov     esi, 1
0x180006c33  jnz     loc_180006D41
0x180006c39  jmp     short loc_180006C43
0x180006c3b  xor     ecx, ecx; dwMilliseconds
0x180006c3d  call    cs:__imp_Sleep
0x180006c43  mov     eax, esi
0x180006c45  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x180006c4b  test    eax, eax
0x180006c4d  jnz     short loc_180006C3B
0x180006c4f  cmp     cs:?g_fLocksInitialized@@3HA, eax; int g_fLocksInitialized
0x180006c55  jnz     loc_180006D39
0x180006c5b  lea     rcx, ModuleName; "kernel32.dll"
0x180006c62  call    cs:__imp_GetModuleHandleW
0x180006c68  mov     rbx, rax
0x180006c6b  test    rax, rax
0x180006c6e  jz      short loc_180006CB7
0x180006c70  lea     rdx, aSwitchtothread; "SwitchToThread"
0x180006c77  mov     rcx, rax; hModule
0x180006c7a  call    cs:__imp_GetProcAddress
0x180006c80  lea     rdx, aTryentercritic; "TryEnterCriticalSection"
0x180006c87  mov     rcx, rbx; hModule
0x180006c8a  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rax; int (*g_pfnSwitchToThread)(void)
0x180006c91  call    cs:__imp_GetProcAddress
0x180006c97  lea     rdx, aSetcriticalsec; "SetCriticalSectionSpinCount"
0x180006c9e  mov     rcx, rbx; hModule
0x180006ca1  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rax; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180006ca8  call    cs:__imp_GetProcAddress
0x180006cae  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180006cb5  jmp     short loc_180006CBE
0x180006cb7  mov     rax, cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180006cbe  cmp     cs:?g_pfnSwitchToThread@@3P6AHXZEA, 0; int (*g_pfnSwitchToThread)(void)
0x180006cc6  jnz     short loc_180006CD6
0x180006cc8  lea     rcx, FakeTryEnterCriticalSection
0x180006ccf  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rcx; int (*g_pfnSwitchToThread)(void)
0x180006cd6  cmp     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, 0; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180006cde  jnz     short loc_180006CEE
0x180006ce0  lea     rcx, FakeTryEnterCriticalSection
0x180006ce7  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rcx; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x180006cee  test    rax, rax
0x180006cf1  jnz     short loc_180006D01
0x180006cf3  lea     rax, FakeTryEnterCriticalSection
0x180006cfa  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x180006d01  cmp     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, 0; int `NumProcessors'::`2'::s_nCPUs
0x180006d08  jnz     short loc_180006D31
0x180006d0a  xorps   xmm0, xmm0
0x180006d0d  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x180006d12  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x180006d17  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180006d1c  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x180006d21  call    cs:__imp_GetSystemInfo
0x180006d27  mov     eax, [rsp+68h+SystemInfo.dwNumberOfProcessors]
0x180006d2b  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x180006d31  mov     eax, esi
0x180006d33  xchg    eax, cs:?g_fLocksInitialized@@3HA; int g_fLocksInitialized
0x180006d39  xor     eax, eax
0x180006d3b  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x180006d41  mov     edx, 80000000h; dwSpinCount
0x180006d46  mov     cs:dword_180010134, 2
0x180006d50  lea     rcx, CriticalSection; lpCriticalSection
0x180006d57  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180006d5d  test    eax, eax
0x180006d5f  jz      loc_180006DE5
0x180006d65  mov     edx, 800003E8h; dwSpinCount
0x180006d6a  mov     cs:dword_180010134, 3
0x180006d74  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006d7b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180006d81  test    eax, eax
0x180006d83  jz      short loc_180006DE5
0x180006d85  mov     cs:?g_fInitCsTimerWrap@@3HA, esi; int g_fInitCsTimerWrap
0x180006d8b  mov     cs:dword_180010134, 5
0x180006d95  call    ?Initialize@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::Initialize(void)
0x180006d9a  test    eax, eax
0x180006d9c  jz      short loc_180006DE5
0x180006d9e  mov     cs:dword_180010134, 6
0x180006da8  call    LKRHashTableInit
0x180006dad  test    al, al
0x180006daf  jz      short loc_180006DE5
0x180006db1  mov     cs:dword_180010134, 7
0x180006dbb  call    ?InitializeStatic@BIG_REF_TRACE@@SAJXZ; BIG_REF_TRACE::InitializeStatic(void)
0x180006dc0  test    eax, eax
0x180006dc2  js      short loc_180006DE5
0x180006dc4  mov     cs:dword_180010134, 8
0x180006dce  call    ?Initialize@EVENT_LOG@@SAJXZ; EVENT_LOG::Initialize(void)
0x180006dd3  test    eax, eax
0x180006dd5  js      short loc_180006DE5
0x180006dd7  mov     cs:dword_180010134, 9
0x180006de1  mov     eax, esi
0x180006de3  jmp     short loc_180006DEC
0x180006de5  call    TerminateIISUtilProcessDetach
0x180006dea  xor     eax, eax
0x180006dec  mov     rbx, [rsp+68h+arg_0]
0x180006df1  add     rsp, 60h
0x180006df5  pop     rsi
0x180006df6  retn
```
