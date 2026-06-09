# wil_details_NtUpdateWnfStateData

- ea: `0x180008bc0`
- end: `0x180008c6a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006bcc`
- `0x180008438`

## callees

- `0x180008bc0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180008bf7`
- `KERNEL32!GetModuleHandleW` at `0x180008bf7`
- `KERNEL32!GetProcAddress` at `0x180008c0e`
- `KERNEL32!GetProcAddress` at `0x180008c0e`

## string_xrefs

- `0x180008bf0`: `ntdll.dll`
- `0x180008c04`: `NtUpdateWnfStateData`

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
0x180008bc0  mov     [rsp+arg_0], rbx
0x180008bc5  mov     [rsp+arg_8], rsi
0x180008bca  push    rdi
0x180008bcb  sub     rsp, 40h
0x180008bcf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008bd6  mov     ebx, r8d
0x180008bd9  mov     rdi, rdx
0x180008bdc  mov     rsi, rcx
0x180008bdf  test    r10, r10
0x180008be2  jnz     short loc_180008C2A
0x180008be4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008beb  test    rax, rax
0x180008bee  jnz     short loc_180008C04
0x180008bf0  lea     rcx, ModuleName; "ntdll.dll"
0x180008bf7  call    cs:__imp_GetModuleHandleW
0x180008bfd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008c04  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008c0b  mov     rcx, rax; hModule
0x180008c0e  call    cs:__imp_GetProcAddress
0x180008c14  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180008c1b  mov     r10, rax
0x180008c1e  test    rax, rax
0x180008c21  jnz     short loc_180008C2A
0x180008c23  mov     eax, 0C0000139h
0x180008c28  jmp     short loc_180008C5A
0x180008c2a  mov     eax, [rsp+48h+arg_30]
0x180008c31  xor     r9d, r9d
0x180008c34  mov     [rsp+48h+var_18], eax
0x180008c38  mov     r8d, ebx
0x180008c3b  mov     eax, [rsp+48h+arg_28]
0x180008c3f  mov     rdx, rdi
0x180008c42  mov     [rsp+48h+var_20], eax
0x180008c46  mov     rcx, rsi
0x180008c49  mov     rax, r10
0x180008c4c  mov     [rsp+48h+var_28], 0
0x180008c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c5a  mov     rbx, [rsp+48h+arg_0]
0x180008c5f  mov     rsi, [rsp+48h+arg_8]
0x180008c64  add     rsp, 40h
0x180008c68  pop     rdi
0x180008c69  retn
```
