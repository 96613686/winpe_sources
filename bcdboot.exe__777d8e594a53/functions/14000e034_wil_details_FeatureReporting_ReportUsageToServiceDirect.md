# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000e034`
- end: `0x14000e0f9`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `197`
- prototype: `_BOOL8 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x14000df08`

## callees

- `0x14000dc30`
- `0x14000e034`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000e0c6`
- `KERNEL32!GetProcAddress` at `0x14000e0c6`
- `KERNEL32!GetModuleHandleW` at `0x14000e0af`
- `KERNEL32!GetModuleHandleW` at `0x14000e0af`

## string_xrefs

- `0x14000e0a8`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, int a3)
{
  __int16 v3; // bx
  int v6; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+34h] [rbp-34h]
  _BYTE v12[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v6 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (__int64)v12,
                     *(volatile signed __int32 **)(a1 + 8),
                     a3,
                     SHIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v10 = *(_DWORD *)(a1 + 24);
    v11 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
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
      ((void (__fastcall *)(int *))ProcAddress)(&v10);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x14000e034  mov     [rsp+arg_18], rbx
0x14000e039  push    rbp
0x14000e03a  push    rsi
0x14000e03b  push    rdi
0x14000e03c  sub     rsp, 50h
0x14000e040  mov     r9, rdx
0x14000e043  mov     rbx, rdx
0x14000e046  mov     rdx, [rcx+8]
0x14000e04a  mov     rsi, rcx
0x14000e04d  shr     r9, 20h
0x14000e051  lea     rcx, [rsp+68h+var_30]
0x14000e056  mov     edi, r8d
0x14000e059  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000e05e  mov     ebp, [rax+10h]
0x14000e061  bt      ebx, 0Ah
0x14000e065  jnb     short loc_14000E0E2
0x14000e067  cmp     edi, 0FEh
0x14000e06d  jz      short loc_14000E0E2
0x14000e06f  mov     eax, [rsi+18h]
0x14000e072  mov     [rsp+68h+var_38], 0
0x14000e07b  mov     dword ptr [rsp+68h+var_38], eax
0x14000e07f  mov     word ptr [rsp+68h+var_38+4], di
0x14000e084  bt      ebx, 0Bh
0x14000e088  jnb     short loc_14000E090
0x14000e08a  or      word ptr [rsp+68h+var_38+6], 1
0x14000e090  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000e097  test    rax, rax
0x14000e09a  jnz     short loc_14000E0D8
0x14000e09c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000e0a3  test    rax, rax
0x14000e0a6  jnz     short loc_14000E0BC
0x14000e0a8  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000e0af  call    cs:__imp_GetModuleHandleW
0x14000e0b5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000e0bc  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000e0c3  mov     rcx, rax; hModule
0x14000e0c6  call    cs:__imp_GetProcAddress
0x14000e0cc  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000e0d3  test    rax, rax
0x14000e0d6  jz      short loc_14000E0E2
0x14000e0d8  lea     rcx, [rsp+68h+var_38]
0x14000e0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0e2  mov     rbx, [rsp+68h+arg_18]
0x14000e0ea  xor     eax, eax
0x14000e0ec  test    ebp, ebp
0x14000e0ee  setz    al
0x14000e0f1  add     rsp, 50h
0x14000e0f5  pop     rdi
0x14000e0f6  pop     rsi
0x14000e0f7  pop     rbp
0x14000e0f8  retn
```
