# wil_details_NtUpdateWnfStateData

- ea: `0x14000c060`
- end: `0x14000c10a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140009e24`
- `0x14000bd90`

## callees

- `0x14000c060`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c097`
- `KERNEL32!GetModuleHandleW` at `0x14000c097`
- `KERNEL32!GetProcAddress` at `0x14000c0ae`
- `KERNEL32!GetProcAddress` at `0x14000c0ae`

## string_xrefs

- `0x14000c090`: `ntdll.dll`
- `0x14000c0a4`: `NtUpdateWnfStateData`

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
0x14000c060  mov     [rsp+arg_0], rbx
0x14000c065  mov     [rsp+arg_8], rsi
0x14000c06a  push    rdi
0x14000c06b  sub     rsp, 40h
0x14000c06f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000c076  mov     ebx, r8d
0x14000c079  mov     rdi, rdx
0x14000c07c  mov     rsi, rcx
0x14000c07f  test    r10, r10
0x14000c082  jnz     short loc_14000C0CA
0x14000c084  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c08b  test    rax, rax
0x14000c08e  jnz     short loc_14000C0A4
0x14000c090  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000c097  call    cs:__imp_GetModuleHandleW
0x14000c09d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c0a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000c0ab  mov     rcx, rax; hModule
0x14000c0ae  call    cs:__imp_GetProcAddress
0x14000c0b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000c0bb  mov     r10, rax
0x14000c0be  test    rax, rax
0x14000c0c1  jnz     short loc_14000C0CA
0x14000c0c3  mov     eax, 0C0000139h
0x14000c0c8  jmp     short loc_14000C0FA
0x14000c0ca  mov     eax, [rsp+48h+arg_30]
0x14000c0d1  xor     r9d, r9d
0x14000c0d4  mov     [rsp+48h+var_18], eax
0x14000c0d8  mov     r8d, ebx
0x14000c0db  mov     eax, [rsp+48h+arg_28]
0x14000c0df  mov     rdx, rdi
0x14000c0e2  mov     [rsp+48h+var_20], eax
0x14000c0e6  mov     rcx, rsi
0x14000c0e9  mov     rax, r10
0x14000c0ec  mov     [rsp+48h+var_28], 0
0x14000c0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0fa  mov     rbx, [rsp+48h+arg_0]
0x14000c0ff  mov     rsi, [rsp+48h+arg_8]
0x14000c104  add     rsp, 40h
0x14000c108  pop     rdi
0x14000c109  retn
```
