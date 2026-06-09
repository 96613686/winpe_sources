# wil_details_NtUpdateWnfStateData

- ea: `0x1800127f0`
- end: `0x18001289a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d5a0`
- `0x1800120e0`

## callees

- `0x1800127f0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001283e`
- `KERNEL32!GetProcAddress` at `0x18001283e`
- `KERNEL32!GetModuleHandleW` at `0x180012827`
- `KERNEL32!GetModuleHandleW` at `0x180012827`

## string_xrefs

- `0x180012820`: `ntdll.dll`
- `0x180012834`: `NtUpdateWnfStateData`

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
0x1800127f0  mov     [rsp+arg_0], rbx
0x1800127f5  mov     [rsp+arg_8], rsi
0x1800127fa  push    rdi
0x1800127fb  sub     rsp, 40h
0x1800127ff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012806  mov     ebx, r8d
0x180012809  mov     rdi, rdx
0x18001280c  mov     rsi, rcx
0x18001280f  test    r10, r10
0x180012812  jnz     short loc_18001285A
0x180012814  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001281b  test    rax, rax
0x18001281e  jnz     short loc_180012834
0x180012820  lea     rcx, ModuleName; "ntdll.dll"
0x180012827  call    cs:__imp_GetModuleHandleW
0x18001282d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012834  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001283b  mov     rcx, rax; hModule
0x18001283e  call    cs:__imp_GetProcAddress
0x180012844  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001284b  mov     r10, rax
0x18001284e  test    rax, rax
0x180012851  jnz     short loc_18001285A
0x180012853  mov     eax, 0C0000139h
0x180012858  jmp     short loc_18001288A
0x18001285a  mov     eax, [rsp+48h+arg_30]
0x180012861  xor     r9d, r9d
0x180012864  mov     [rsp+48h+var_18], eax
0x180012868  mov     r8d, ebx
0x18001286b  mov     eax, [rsp+48h+arg_28]
0x18001286f  mov     rdx, rdi
0x180012872  mov     [rsp+48h+var_20], eax
0x180012876  mov     rcx, rsi
0x180012879  mov     rax, r10
0x18001287c  mov     [rsp+48h+var_28], 0
0x180012885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001288a  mov     rbx, [rsp+48h+arg_0]
0x18001288f  mov     rsi, [rsp+48h+arg_8]
0x180012894  add     rsp, 40h
0x180012898  pop     rdi
0x180012899  retn
```
