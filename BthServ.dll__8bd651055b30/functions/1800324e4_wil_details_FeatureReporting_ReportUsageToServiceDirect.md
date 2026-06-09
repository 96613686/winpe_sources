# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800324e4`
- end: `0x18003260d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800323c8`

## callees

- `0x180001790`
- `0x180011b14`
- `0x1800324e4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800325b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800325b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800325c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800325c9`

## string_xrefs

- `0x1800325ab`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v4; // edi
  __int64 v5; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v10[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v11; // [rsp+50h] [rbp-28h] BYREF
  __int64 v12; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v4 = a3;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(v10, &Feature_UDFDOD__private_reporting, a3, HIDWORD(a2));
  v11 = *(_OWORD *)v5;
  v12 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(54591346, v4, 1, &Feature_UDFDOD__private_reporting, &v11);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 54591346;
    WORD2(v9) = v4;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_11;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_11:
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v9);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x1800324e4  mov     [rsp+arg_0], rbx
0x1800324e9  mov     [rsp+arg_18], rsi
0x1800324ee  push    rdi
0x1800324ef  sub     rsp, 70h
0x1800324f3  mov     rax, cs:__security_cookie
0x1800324fa  xor     rax, rsp
0x1800324fd  mov     [rsp+78h+var_10], rax
0x180032502  mov     r9, rdx
0x180032505  lea     rcx, [rsp+78h+var_40]
0x18003250a  mov     rbx, rdx
0x18003250d  shr     r9, 20h
0x180032511  mov     rdx, cs:off_180040D88
0x180032518  mov     edi, r8d
0x18003251b  call    wil_details_FeatureReporting_RecordUsageInCache
0x180032520  mov     esi, 1
0x180032525  movups  xmm1, xmmword ptr [rax]
0x180032528  movups  [rsp+78h+var_28], xmm1
0x18003252d  movsd   xmm0, qword ptr [rax+10h]
0x180032532  mov     rax, cs:g_wil_details_recordFeatureUsage
0x180032539  movsd   [rsp+78h+var_18], xmm0
0x18003253f  test    rax, rax
0x180032542  jz      short loc_180032564
0x180032544  mov     r9, cs:off_180040D88
0x18003254b  lea     rcx, [rsp+78h+var_28]
0x180032550  mov     [rsp+78h+var_58], rcx
0x180032555  mov     r8d, esi
0x180032558  mov     ecx, 340FF72h
0x18003255d  mov     edx, edi
0x18003255f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032564  bt      ebx, 0Ah
0x180032568  jnb     short loc_1800325E5
0x18003256a  cmp     edi, 0FEh
0x180032570  jz      short loc_1800325E5
0x180032572  mov     [rsp+78h+var_48], 0
0x18003257b  mov     dword ptr [rsp+78h+var_48], 340FF72h
0x180032583  mov     word ptr [rsp+78h+var_48+4], di
0x180032588  bt      ebx, 0Bh
0x18003258c  jnb     short loc_180032593
0x18003258e  or      word ptr [rsp+78h+var_48+6], si
0x180032593  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18003259a  test    rax, rax
0x18003259d  jnz     short loc_1800325DB
0x18003259f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800325a6  test    rax, rax
0x1800325a9  jnz     short loc_1800325BF
0x1800325ab  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800325b2  call    cs:__imp_GetModuleHandleW
0x1800325b8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800325bf  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800325c6  mov     rcx, rax; hModule
0x1800325c9  call    cs:__imp_GetProcAddress
0x1800325cf  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800325d6  test    rax, rax
0x1800325d9  jz      short loc_1800325E5
0x1800325db  lea     rcx, [rsp+78h+var_48]
0x1800325e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325e5  xor     eax, eax
0x1800325e7  cmp     dword ptr [rsp+78h+var_18], eax
0x1800325eb  setz    al
0x1800325ee  mov     rcx, [rsp+78h+var_10]
0x1800325f3  xor     rcx, rsp; StackCookie
0x1800325f6  call    __security_check_cookie
0x1800325fb  lea     r11, [rsp+78h+var_8]
0x180032600  mov     rbx, [r11+10h]
0x180032604  mov     rsi, [r11+28h]
0x180032608  mov     rsp, r11
0x18003260b  pop     rdi
0x18003260c  retn
```
