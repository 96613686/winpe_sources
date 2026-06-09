# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800032e4`
- end: `0x1800033ad`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `201`
- prototype: `_BOOL8 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800031c8`

## callees

- `0x180002ef0`
- `0x1800032e4`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180003363`
- `KERNEL32!GetModuleHandleW` at `0x180003363`
- `KERNEL32!GetProcAddress` at `0x18000337a`
- `KERNEL32!GetProcAddress` at `0x18000337a`

## string_xrefs

- `0x18000335c`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, int a3)
{
  __int16 v3; // bx
  int v5; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v5 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (__int64)v10,
                     (volatile signed __int32 *)&Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_reporting,
                     a3,
                     SHIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v9 = 57741219;
    WORD2(v9) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_9:
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v9);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x1800032e4  mov     [rsp+arg_0], rbx
0x1800032e9  mov     [rsp+arg_18], rsi
0x1800032ee  push    rdi
0x1800032ef  sub     rsp, 50h
0x1800032f3  mov     r9, rdx
0x1800032f6  lea     rcx, [rsp+58h+var_20]
0x1800032fb  mov     rbx, rdx
0x1800032fe  shr     r9, 20h
0x180003302  mov     rdx, cs:off_18006EB50
0x180003309  mov     edi, r8d
0x18000330c  call    wil_details_FeatureReporting_RecordUsageInCache
0x180003311  mov     esi, [rax+10h]
0x180003314  bt      ebx, 0Ah
0x180003318  jnb     short loc_180003396
0x18000331a  cmp     edi, 0FEh
0x180003320  jz      short loc_180003396
0x180003322  mov     [rsp+58h+var_28], 0
0x18000332b  mov     dword ptr [rsp+58h+var_28], 3710FA3h
0x180003333  mov     word ptr [rsp+58h+var_28+4], di
0x180003338  bt      ebx, 0Bh
0x18000333c  jnb     short loc_180003344
0x18000333e  or      word ptr [rsp+58h+var_28+6], 1
0x180003344  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000334b  test    rax, rax
0x18000334e  jnz     short loc_18000338C
0x180003350  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180003357  test    rax, rax
0x18000335a  jnz     short loc_180003370
0x18000335c  lea     rcx, ModuleName; "ntdll.dll"
0x180003363  call    cs:__imp_GetModuleHandleW
0x180003369  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180003370  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180003377  mov     rcx, rax; hModule
0x18000337a  call    cs:__imp_GetProcAddress
0x180003380  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180003387  test    rax, rax
0x18000338a  jz      short loc_180003396
0x18000338c  lea     rcx, [rsp+58h+var_28]
0x180003391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003396  mov     rbx, [rsp+58h+arg_0]
0x18000339b  xor     eax, eax
0x18000339d  test    esi, esi
0x18000339f  mov     rsi, [rsp+58h+arg_18]
0x1800033a4  setz    al
0x1800033a7  add     rsp, 50h
0x1800033ab  pop     rdi
0x1800033ac  retn
```
