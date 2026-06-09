# wil_details_NtUpdateWnfStateData

- ea: `0x180029914`
- end: `0x1800299cb`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180027550`
- `0x180028fa4`

## callees

- `0x180029914`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002994b`
- `KERNEL32!GetModuleHandleW` at `0x18002994b`
- `KERNEL32!GetProcAddress` at `0x180029968`
- `KERNEL32!GetProcAddress` at `0x180029968`

## string_xrefs

- `0x180029944`: `ntdll.dll`
- `0x18002995e`: `NtUpdateWnfStateData`

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
0x180029914  mov     [rsp+arg_0], rbx
0x180029919  mov     [rsp+arg_8], rsi
0x18002991e  push    rdi
0x18002991f  sub     rsp, 40h
0x180029923  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002992a  mov     ebx, r8d
0x18002992d  mov     rdi, rdx
0x180029930  mov     rsi, rcx
0x180029933  test    r10, r10
0x180029936  jnz     short loc_18002998A
0x180029938  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002993f  test    rax, rax
0x180029942  jnz     short loc_18002995E
0x180029944  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002994b  call    cs:__imp_GetModuleHandleW
0x180029952  nop     dword ptr [rax+rax+00h]
0x180029957  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002995e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180029965  mov     rcx, rax; hModule
0x180029968  call    cs:__imp_GetProcAddress
0x18002996f  nop     dword ptr [rax+rax+00h]
0x180029974  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002997b  mov     r10, rax
0x18002997e  test    rax, rax
0x180029981  jnz     short loc_18002998A
0x180029983  mov     eax, 0C0000139h
0x180029988  jmp     short loc_1800299BA
0x18002998a  mov     eax, [rsp+48h+arg_30]
0x180029991  xor     r9d, r9d
0x180029994  mov     [rsp+48h+var_18], eax
0x180029998  mov     r8d, ebx
0x18002999b  mov     eax, [rsp+48h+arg_28]
0x18002999f  mov     rdx, rdi
0x1800299a2  mov     [rsp+48h+var_20], eax
0x1800299a6  mov     rcx, rsi
0x1800299a9  mov     rax, r10
0x1800299ac  mov     [rsp+48h+var_28], 0
0x1800299b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ba  mov     rbx, [rsp+48h+arg_0]
0x1800299bf  mov     rsi, [rsp+48h+arg_8]
0x1800299c4  add     rsp, 40h
0x1800299c8  pop     rdi
0x1800299c9  retn
```
