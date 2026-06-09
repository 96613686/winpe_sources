# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000e888`
- end: `0x18000e966`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18000ec2c`

## callees

- `0x18000e5ac`
- `0x18000e888`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e90f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e90f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e92c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e92c`

## string_xrefs

- `0x18000e908`: `ntdll.dll`

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
                     &Feature_WcRemoveFileOwnershipTOCTOU__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 50974410;
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
0x18000e888  mov     [rsp+arg_0], rbx
0x18000e88d  mov     [rsp+arg_18], rsi
0x18000e892  push    rdi
0x18000e893  sub     rsp, 50h
0x18000e897  mov     r9, rdx
0x18000e89a  lea     rcx, [rsp+58h+var_20]
0x18000e89f  mov     rbx, rdx
0x18000e8a2  shr     r9, 20h
0x18000e8a6  mov     rdx, cs:off_180047AB8
0x18000e8ad  mov     edi, r8d
0x18000e8b0  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000e8b5  mov     esi, [rax+10h]
0x18000e8b8  bt      ebx, 0Ah
0x18000e8bc  jnb     loc_18000E94E
0x18000e8c2  cmp     edi, 0FEh
0x18000e8c8  jz      loc_18000E94E
0x18000e8ce  mov     [rsp+58h+var_28], 0
0x18000e8d7  mov     dword ptr [rsp+58h+var_28], 309CECAh
0x18000e8df  mov     word ptr [rsp+58h+var_28+4], di
0x18000e8e4  bt      ebx, 0Bh
0x18000e8e8  jnb     short loc_18000E8F0
0x18000e8ea  or      word ptr [rsp+58h+var_28+6], 1
0x18000e8f0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000e8f7  test    rax, rax
0x18000e8fa  jnz     short loc_18000E944
0x18000e8fc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000e903  test    rax, rax
0x18000e906  jnz     short loc_18000E922
0x18000e908  lea     rcx, ModuleName; "ntdll.dll"
0x18000e90f  call    cs:__imp_GetModuleHandleW
0x18000e916  nop     dword ptr [rax+rax+00h]
0x18000e91b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000e922  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000e929  mov     rcx, rax; hModule
0x18000e92c  call    cs:__imp_GetProcAddress
0x18000e933  nop     dword ptr [rax+rax+00h]
0x18000e938  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000e93f  test    rax, rax
0x18000e942  jz      short loc_18000E94E
0x18000e944  lea     rcx, [rsp+58h+var_28]
0x18000e949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94e  mov     rbx, [rsp+58h+arg_0]
0x18000e953  xor     eax, eax
0x18000e955  test    esi, esi
0x18000e957  mov     rsi, [rsp+58h+arg_18]
0x18000e95c  setz    al
0x18000e95f  add     rsp, 50h
0x18000e963  pop     rdi
0x18000e964  retn
```
