# wil_details_NtUpdateWnfStateData

- ea: `0x140073384`
- end: `0x14007343b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14006f6b0`
- `0x14007195c`

## callees

- `0x140073384`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400733d8`
- `KERNEL32!GetProcAddress` at `0x1400733d8`
- `KERNEL32!GetModuleHandleW` at `0x1400733bb`
- `KERNEL32!GetModuleHandleW` at `0x1400733bb`

## string_xrefs

- `0x1400733b4`: `ntdll.dll`
- `0x1400733ce`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x140073384  mov     [rsp+arg_0], rbx
0x140073389  mov     [rsp+arg_8], rsi
0x14007338e  push    rdi
0x14007338f  sub     rsp, 40h
0x140073393  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14007339a  mov     ebx, r8d
0x14007339d  mov     rdi, rdx
0x1400733a0  mov     rsi, rcx
0x1400733a3  test    r10, r10
0x1400733a6  jnz     short loc_1400733FA
0x1400733a8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400733af  test    rax, rax
0x1400733b2  jnz     short loc_1400733CE
0x1400733b4  lea     rcx, ModuleName; "ntdll.dll"
0x1400733bb  call    cs:__imp_GetModuleHandleW
0x1400733c2  nop     dword ptr [rax+rax+00h]
0x1400733c7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400733ce  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1400733d5  mov     rcx, rax; hModule
0x1400733d8  call    cs:__imp_GetProcAddress
0x1400733df  nop     dword ptr [rax+rax+00h]
0x1400733e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1400733eb  mov     r10, rax
0x1400733ee  test    rax, rax
0x1400733f1  jnz     short loc_1400733FA
0x1400733f3  mov     eax, 0C0000139h
0x1400733f8  jmp     short loc_14007342A
0x1400733fa  mov     eax, [rsp+48h+arg_30]
0x140073401  xor     r9d, r9d
0x140073404  mov     [rsp+48h+var_18], eax
0x140073408  mov     r8d, ebx
0x14007340b  mov     eax, [rsp+48h+arg_28]
0x14007340f  mov     rdx, rdi
0x140073412  mov     [rsp+48h+var_20], eax
0x140073416  mov     rcx, rsi
0x140073419  mov     rax, r10
0x14007341c  mov     [rsp+48h+var_28], 0
0x140073425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007342a  mov     rbx, [rsp+48h+arg_0]
0x14007342f  mov     rsi, [rsp+48h+arg_8]
0x140073434  add     rsp, 40h
0x140073438  pop     rdi
0x140073439  retn
```
