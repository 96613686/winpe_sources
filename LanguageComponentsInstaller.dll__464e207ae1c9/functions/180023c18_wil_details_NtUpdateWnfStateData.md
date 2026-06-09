# wil_details_NtUpdateWnfStateData

- ea: `0x180023c18`
- end: `0x180023cc2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001a5e4`
- `0x180022b68`

## callees

- `0x180023c18`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023c4f`

## string_xrefs

- `0x180023c48`: `ntdll.dll`
- `0x180023c5c`: `NtUpdateWnfStateData`

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
0x180023c18  mov     [rsp+arg_0], rbx
0x180023c1d  mov     [rsp+arg_8], rsi
0x180023c22  push    rdi
0x180023c23  sub     rsp, 40h
0x180023c27  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180023c2e  mov     ebx, r8d
0x180023c31  mov     rdi, rdx
0x180023c34  mov     rsi, rcx
0x180023c37  test    r10, r10
0x180023c3a  jnz     short loc_180023C82
0x180023c3c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023c43  test    rax, rax
0x180023c46  jnz     short loc_180023C5C
0x180023c48  lea     rcx, ModuleName; "ntdll.dll"
0x180023c4f  call    cs:__imp_GetModuleHandleW
0x180023c55  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023c5c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180023c63  mov     rcx, rax; hModule
0x180023c66  call    cs:__imp_GetProcAddress
0x180023c6c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180023c73  mov     r10, rax
0x180023c76  test    rax, rax
0x180023c79  jnz     short loc_180023C82
0x180023c7b  mov     eax, 0C0000139h
0x180023c80  jmp     short loc_180023CB2
0x180023c82  mov     eax, [rsp+48h+arg_30]
0x180023c89  xor     r9d, r9d
0x180023c8c  mov     [rsp+48h+var_18], eax
0x180023c90  mov     r8d, ebx
0x180023c93  mov     eax, [rsp+48h+arg_28]
0x180023c97  mov     rdx, rdi
0x180023c9a  mov     [rsp+48h+var_20], eax
0x180023c9e  mov     rcx, rsi
0x180023ca1  mov     rax, r10
0x180023ca4  mov     [rsp+48h+var_28], 0
0x180023cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cb2  mov     rbx, [rsp+48h+arg_0]
0x180023cb7  mov     rsi, [rsp+48h+arg_8]
0x180023cbc  add     rsp, 40h
0x180023cc0  pop     rdi
0x180023cc1  retn
```
