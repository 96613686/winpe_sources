# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18003bcd4`
- end: `0x18003bdb2`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18003bbb4`

## callees

- `0x18003b8d8`
- `0x18003bcd4`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003bd78`
- `KERNEL32!GetProcAddress` at `0x18003bd78`
- `KERNEL32!GetModuleHandleW` at `0x18003bd5b`
- `KERNEL32!GetModuleHandleW` at `0x18003bd5b`

## string_xrefs

- `0x18003bd54`: `ntdll.dll`

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
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18003bcd4  mov     [rsp+arg_0], rbx
0x18003bcd9  mov     [rsp+arg_18], rsi
0x18003bcde  push    rdi
0x18003bcdf  sub     rsp, 50h
0x18003bce3  mov     r9, rdx
0x18003bce6  lea     rcx, [rsp+58h+var_20]
0x18003bceb  mov     rbx, rdx
0x18003bcee  shr     r9, 20h
0x18003bcf2  mov     rdx, cs:off_18004A938
0x18003bcf9  mov     edi, r8d
0x18003bcfc  call    wil_details_FeatureReporting_RecordUsageInCache
0x18003bd01  mov     esi, [rax+10h]
0x18003bd04  bt      ebx, 0Ah
0x18003bd08  jnb     loc_18003BD9A
0x18003bd0e  cmp     edi, 0FEh
0x18003bd14  jz      loc_18003BD9A
0x18003bd1a  mov     [rsp+58h+var_28], 0
0x18003bd23  mov     dword ptr [rsp+58h+var_28], 3710FA3h
0x18003bd2b  mov     word ptr [rsp+58h+var_28+4], di
0x18003bd30  bt      ebx, 0Bh
0x18003bd34  jnb     short loc_18003BD3C
0x18003bd36  or      word ptr [rsp+58h+var_28+6], 1
0x18003bd3c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18003bd43  test    rax, rax
0x18003bd46  jnz     short loc_18003BD90
0x18003bd48  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003bd4f  test    rax, rax
0x18003bd52  jnz     short loc_18003BD6E
0x18003bd54  lea     rcx, ModuleName; "ntdll.dll"
0x18003bd5b  call    cs:__imp_GetModuleHandleW
0x18003bd62  nop     dword ptr [rax+rax+00h]
0x18003bd67  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003bd6e  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18003bd75  mov     rcx, rax; hModule
0x18003bd78  call    cs:__imp_GetProcAddress
0x18003bd7f  nop     dword ptr [rax+rax+00h]
0x18003bd84  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18003bd8b  test    rax, rax
0x18003bd8e  jz      short loc_18003BD9A
0x18003bd90  lea     rcx, [rsp+58h+var_28]
0x18003bd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd9a  mov     rbx, [rsp+58h+arg_0]
0x18003bd9f  xor     eax, eax
0x18003bda1  test    esi, esi
0x18003bda3  mov     rsi, [rsp+58h+arg_18]
0x18003bda8  setz    al
0x18003bdab  add     rsp, 50h
0x18003bdaf  pop     rdi
0x18003bdb0  retn
```
