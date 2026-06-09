# wil_details_NtQueryWnfStateData

- ea: `0x18002986c`
- end: `0x18002990d`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027550`
- `0x180028fa4`

## callees

- `0x18002986c`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002989b`
- `KERNEL32!GetModuleHandleW` at `0x18002989b`
- `KERNEL32!GetProcAddress` at `0x1800298b8`
- `KERNEL32!GetProcAddress` at `0x1800298b8`

## string_xrefs

- `0x180029894`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64, __int64, __int64); // r10
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18002986c  mov     [rsp+arg_0], rbx
0x180029871  push    rdi
0x180029872  sub     rsp, 40h
0x180029876  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18002987d  mov     rbx, r9
0x180029880  mov     rdi, rcx
0x180029883  test    r10, r10
0x180029886  jnz     short loc_1800298DA
0x180029888  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002988f  test    rax, rax
0x180029892  jnz     short loc_1800298AE
0x180029894  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002989b  call    cs:__imp_GetModuleHandleW
0x1800298a2  nop     dword ptr [rax+rax+00h]
0x1800298a7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800298ae  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800298b5  mov     rcx, rax; hModule
0x1800298b8  call    cs:__imp_GetProcAddress
0x1800298bf  nop     dword ptr [rax+rax+00h]
0x1800298c4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800298cb  mov     r10, rax
0x1800298ce  test    rax, rax
0x1800298d1  jnz     short loc_1800298DA
0x1800298d3  mov     eax, 0C0000139h
0x1800298d8  jmp     short loc_180029901
0x1800298da  mov     rax, [rsp+48h+arg_28]
0x1800298df  mov     r9, rbx
0x1800298e2  mov     [rsp+48h+var_20], rax
0x1800298e7  xor     r8d, r8d
0x1800298ea  mov     rax, [rsp+48h+arg_20]
0x1800298ef  xor     edx, edx
0x1800298f1  mov     [rsp+48h+var_28], rax
0x1800298f6  mov     rcx, rdi
0x1800298f9  mov     rax, r10
0x1800298fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029901  mov     rbx, [rsp+48h+arg_0]
0x180029906  add     rsp, 40h
0x18002990a  pop     rdi
0x18002990b  retn
```
