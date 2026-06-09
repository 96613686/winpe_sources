# wil_details_NtQueryWnfStateData

- ea: `0x180010e64`
- end: `0x180010f05`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e094`
- `0x1800109bc`

## callees

- `0x180010e64`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010eb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010eb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010e93`

## string_xrefs

- `0x180010e8c`: `ntdll.dll`

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
0x180010e64  mov     [rsp+arg_0], rbx
0x180010e69  push    rdi
0x180010e6a  sub     rsp, 40h
0x180010e6e  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180010e75  mov     rbx, r9
0x180010e78  mov     rdi, rcx
0x180010e7b  test    r10, r10
0x180010e7e  jnz     short loc_180010ED2
0x180010e80  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010e87  test    rax, rax
0x180010e8a  jnz     short loc_180010EA6
0x180010e8c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180010e93  call    cs:__imp_GetModuleHandleW
0x180010e9a  nop     dword ptr [rax+rax+00h]
0x180010e9f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010ea6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180010ead  mov     rcx, rax; hModule
0x180010eb0  call    cs:__imp_GetProcAddress
0x180010eb7  nop     dword ptr [rax+rax+00h]
0x180010ebc  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180010ec3  mov     r10, rax
0x180010ec6  test    rax, rax
0x180010ec9  jnz     short loc_180010ED2
0x180010ecb  mov     eax, 0C0000139h
0x180010ed0  jmp     short loc_180010EF9
0x180010ed2  mov     rax, [rsp+48h+arg_28]
0x180010ed7  mov     r9, rbx
0x180010eda  mov     [rsp+48h+var_20], rax
0x180010edf  xor     r8d, r8d
0x180010ee2  mov     rax, [rsp+48h+arg_20]
0x180010ee7  xor     edx, edx
0x180010ee9  mov     [rsp+48h+var_28], rax
0x180010eee  mov     rcx, rdi
0x180010ef1  mov     rax, r10
0x180010ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef9  mov     rbx, [rsp+48h+arg_0]
0x180010efe  add     rsp, 40h
0x180010f02  pop     rdi
0x180010f03  retn
```
