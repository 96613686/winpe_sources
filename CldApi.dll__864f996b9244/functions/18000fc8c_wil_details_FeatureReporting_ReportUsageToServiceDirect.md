# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000fc8c`
- end: `0x18000fd55`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000fb70`

## callees

- `0x18000f898`
- `0x18000fc8c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd22`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fd0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fd0b`

## string_xrefs

- `0x18000fd04`: `ntdll.dll`

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
                     &Feature_57207774__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 57207774;
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
0x18000fc8c  mov     [rsp+arg_0], rbx
0x18000fc91  mov     [rsp+arg_18], rsi
0x18000fc96  push    rdi
0x18000fc97  sub     rsp, 50h
0x18000fc9b  mov     r9, rdx
0x18000fc9e  lea     rcx, [rsp+58h+var_20]
0x18000fca3  mov     rbx, rdx
0x18000fca6  shr     r9, 20h
0x18000fcaa  mov     rdx, cs:off_180025E48
0x18000fcb1  mov     edi, r8d
0x18000fcb4  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000fcb9  mov     esi, [rax+10h]
0x18000fcbc  bt      ebx, 0Ah
0x18000fcc0  jnb     short loc_18000FD3E
0x18000fcc2  cmp     edi, 0FEh
0x18000fcc8  jz      short loc_18000FD3E
0x18000fcca  mov     [rsp+58h+var_28], 0
0x18000fcd3  mov     dword ptr [rsp+58h+var_28], 368EBDEh
0x18000fcdb  mov     word ptr [rsp+58h+var_28+4], di
0x18000fce0  bt      ebx, 0Bh
0x18000fce4  jnb     short loc_18000FCEC
0x18000fce6  or      word ptr [rsp+58h+var_28+6], 1
0x18000fcec  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000fcf3  test    rax, rax
0x18000fcf6  jnz     short loc_18000FD34
0x18000fcf8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000fcff  test    rax, rax
0x18000fd02  jnz     short loc_18000FD18
0x18000fd04  lea     rcx, ModuleName; "ntdll.dll"
0x18000fd0b  call    cs:__imp_GetModuleHandleW
0x18000fd11  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000fd18  lea     rdx, ProcName; "RtlNotifyFeatureUsage"
0x18000fd1f  mov     rcx, rax; hModule
0x18000fd22  call    cs:__imp_GetProcAddress
0x18000fd28  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000fd2f  test    rax, rax
0x18000fd32  jz      short loc_18000FD3E
0x18000fd34  lea     rcx, [rsp+58h+var_28]
0x18000fd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd3e  mov     rbx, [rsp+58h+arg_0]
0x18000fd43  xor     eax, eax
0x18000fd45  test    esi, esi
0x18000fd47  mov     rsi, [rsp+58h+arg_18]
0x18000fd4c  setz    al
0x18000fd4f  add     rsp, 50h
0x18000fd53  pop     rdi
0x18000fd54  retn
```
