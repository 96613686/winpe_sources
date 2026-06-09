# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180028b94`
- end: `0x180028cbd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180028a78`

## callees

- `0x180002350`
- `0x180023678`
- `0x180028b94`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028c79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028c79`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028c62`

## string_xrefs

- `0x180028c5b`: `ntdll.dll`

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
  v5 = wil_details_FeatureReporting_RecordUsageInCache(v10, &Feature_ShadowAdmin__private_reporting, a3, HIDWORD(a2));
  v11 = *(_OWORD *)v5;
  v12 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(60288851, v4, 1, &Feature_ShadowAdmin__private_reporting, &v11);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v9 = 60288851;
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
0x180028b94  mov     [rsp+arg_0], rbx
0x180028b99  mov     [rsp+arg_18], rsi
0x180028b9e  push    rdi
0x180028b9f  sub     rsp, 70h
0x180028ba3  mov     rax, cs:__security_cookie
0x180028baa  xor     rax, rsp
0x180028bad  mov     [rsp+78h+var_10], rax
0x180028bb2  mov     r9, rdx
0x180028bb5  lea     rcx, [rsp+78h+var_40]
0x180028bba  mov     rbx, rdx
0x180028bbd  shr     r9, 20h
0x180028bc1  mov     rdx, cs:off_18004F058
0x180028bc8  mov     edi, r8d
0x180028bcb  call    wil_details_FeatureReporting_RecordUsageInCache
0x180028bd0  mov     esi, 1
0x180028bd5  movups  xmm1, xmmword ptr [rax]
0x180028bd8  movups  [rsp+78h+var_28], xmm1
0x180028bdd  movsd   xmm0, qword ptr [rax+10h]
0x180028be2  mov     rax, cs:g_wil_details_recordFeatureUsage
0x180028be9  movsd   [rsp+78h+var_18], xmm0
0x180028bef  test    rax, rax
0x180028bf2  jz      short loc_180028C14
0x180028bf4  mov     r9, cs:off_18004F058
0x180028bfb  lea     rcx, [rsp+78h+var_28]
0x180028c00  mov     [rsp+78h+var_58], rcx
0x180028c05  mov     r8d, esi
0x180028c08  mov     ecx, 397EF53h
0x180028c0d  mov     edx, edi
0x180028c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c14  bt      ebx, 0Ah
0x180028c18  jnb     short loc_180028C95
0x180028c1a  cmp     edi, 0FEh
0x180028c20  jz      short loc_180028C95
0x180028c22  mov     [rsp+78h+var_48], 0
0x180028c2b  mov     dword ptr [rsp+78h+var_48], 397EF53h
0x180028c33  mov     word ptr [rsp+78h+var_48+4], di
0x180028c38  bt      ebx, 0Bh
0x180028c3c  jnb     short loc_180028C43
0x180028c3e  or      word ptr [rsp+78h+var_48+6], si
0x180028c43  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180028c4a  test    rax, rax
0x180028c4d  jnz     short loc_180028C8B
0x180028c4f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028c56  test    rax, rax
0x180028c59  jnz     short loc_180028C6F
0x180028c5b  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180028c62  call    cs:__imp_GetModuleHandleW
0x180028c68  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028c6f  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180028c76  mov     rcx, rax; hModule
0x180028c79  call    cs:__imp_GetProcAddress
0x180028c7f  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180028c86  test    rax, rax
0x180028c89  jz      short loc_180028C95
0x180028c8b  lea     rcx, [rsp+78h+var_48]
0x180028c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c95  xor     eax, eax
0x180028c97  cmp     dword ptr [rsp+78h+var_18], eax
0x180028c9b  setz    al
0x180028c9e  mov     rcx, [rsp+78h+var_10]
0x180028ca3  xor     rcx, rsp; StackCookie
0x180028ca6  call    __security_check_cookie
0x180028cab  lea     r11, [rsp+78h+var_8]
0x180028cb0  mov     rbx, [r11+10h]
0x180028cb4  mov     rsi, [r11+28h]
0x180028cb8  mov     rsp, r11
0x180028cbb  pop     rdi
0x180028cbc  retn
```
