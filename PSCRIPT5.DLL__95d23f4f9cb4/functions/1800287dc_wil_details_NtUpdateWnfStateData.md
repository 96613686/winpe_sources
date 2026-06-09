# wil_details_NtUpdateWnfStateData

- ea: `0x1800287dc`
- end: `0x180028886`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800267d4`
- `0x180027f14`

## callees

- `0x1800287dc`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180028813`
- `KERNEL32!GetModuleHandleW` at `0x180028813`
- `KERNEL32!GetProcAddress` at `0x18002882a`
- `KERNEL32!GetProcAddress` at `0x18002882a`

## string_xrefs

- `0x18002880c`: `ntdll.dll`
- `0x180028820`: `NtUpdateWnfStateData`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x1800287dc  mov     [rsp+arg_0], rbx
0x1800287e1  mov     [rsp+arg_8], rsi
0x1800287e6  push    rdi
0x1800287e7  sub     rsp, 40h
0x1800287eb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800287f2  mov     ebx, r8d
0x1800287f5  mov     rdi, rdx
0x1800287f8  mov     rsi, rcx
0x1800287fb  test    r10, r10
0x1800287fe  jnz     short loc_180028846
0x180028800  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028807  test    rax, rax
0x18002880a  jnz     short loc_180028820
0x18002880c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180028813  call    cs:__imp_GetModuleHandleW
0x180028819  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028820  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180028827  mov     rcx, rax; hModule
0x18002882a  call    cs:__imp_GetProcAddress
0x180028830  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180028837  mov     r10, rax
0x18002883a  test    rax, rax
0x18002883d  jnz     short loc_180028846
0x18002883f  mov     eax, 0C0000139h
0x180028844  jmp     short loc_180028876
0x180028846  mov     eax, [rsp+48h+arg_30]
0x18002884d  xor     r9d, r9d
0x180028850  mov     [rsp+48h+var_18], eax
0x180028854  mov     r8d, ebx
0x180028857  mov     eax, [rsp+48h+arg_28]
0x18002885b  mov     rdx, rdi
0x18002885e  mov     [rsp+48h+var_20], eax
0x180028862  mov     rcx, rsi
0x180028865  mov     rax, r10
0x180028868  mov     [rsp+48h+var_28], 0
0x180028871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028876  mov     rbx, [rsp+48h+arg_0]
0x18002887b  mov     rsi, [rsp+48h+arg_8]
0x180028880  add     rsp, 40h
0x180028884  pop     rdi
0x180028885  retn
```
