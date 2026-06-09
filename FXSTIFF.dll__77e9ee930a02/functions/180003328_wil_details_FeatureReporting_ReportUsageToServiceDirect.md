# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180003328`
- end: `0x180003406`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180003208`

## callees

- `0x180002f2c`
- `0x180003328`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800033af`
- `KERNEL32!GetModuleHandleW` at `0x1800033af`
- `KERNEL32!GetProcAddress` at `0x1800033cc`
- `KERNEL32!GetProcAddress` at `0x1800033cc`

## string_xrefs

- `0x1800033a8`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v4; // edi
  int v5; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v4 = a3;
  v5 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     v10,
                     &Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 57741219;
    WORD2(v9) = v4;
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
0x180003328  mov     [rsp+arg_0], rbx
0x18000332d  mov     [rsp+arg_18], rsi
0x180003332  push    rdi
0x180003333  sub     rsp, 50h
0x180003337  mov     r9, rdx
0x18000333a  lea     rcx, [rsp+58h+var_20]
0x18000333f  mov     rbx, rdx
0x180003342  shr     r9, 20h
0x180003346  mov     rdx, cs:off_18006EB90
0x18000334d  mov     edi, r8d
0x180003350  call    wil_details_FeatureReporting_RecordUsageInCache
0x180003355  mov     esi, [rax+10h]
0x180003358  bt      ebx, 0Ah
0x18000335c  jnb     loc_1800033EE
0x180003362  cmp     edi, 0FEh
0x180003368  jz      loc_1800033EE
0x18000336e  mov     [rsp+58h+var_28], 0
0x180003377  mov     dword ptr [rsp+58h+var_28], 3710FA3h
0x18000337f  mov     word ptr [rsp+58h+var_28+4], di
0x180003384  bt      ebx, 0Bh
0x180003388  jnb     short loc_180003390
0x18000338a  or      word ptr [rsp+58h+var_28+6], 1
0x180003390  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180003397  test    rax, rax
0x18000339a  jnz     short loc_1800033E4
0x18000339c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800033a3  test    rax, rax
0x1800033a6  jnz     short loc_1800033C2
0x1800033a8  lea     rcx, ModuleName; "ntdll.dll"
0x1800033af  call    cs:__imp_GetModuleHandleW
0x1800033b6  nop     dword ptr [rax+rax+00h]
0x1800033bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800033c2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800033c9  mov     rcx, rax; hModule
0x1800033cc  call    cs:__imp_GetProcAddress
0x1800033d3  nop     dword ptr [rax+rax+00h]
0x1800033d8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800033df  test    rax, rax
0x1800033e2  jz      short loc_1800033EE
0x1800033e4  lea     rcx, [rsp+58h+var_28]
0x1800033e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ee  mov     rbx, [rsp+58h+arg_0]
0x1800033f3  xor     eax, eax
0x1800033f5  test    esi, esi
0x1800033f7  mov     rsi, [rsp+58h+arg_18]
0x1800033fc  setz    al
0x1800033ff  add     rsp, 50h
0x180003403  pop     rdi
0x180003404  retn
```
