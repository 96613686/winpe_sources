# wil_details_NtUpdateWnfStateData

- ea: `0x14000d07c`
- end: `0x14000d126`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b888`
- `0x14000ce3c`

## callees

- `0x14000d07c`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000d0b3`
- `KERNEL32!GetModuleHandleW` at `0x14000d0b3`
- `KERNEL32!GetProcAddress` at `0x14000d0ca`
- `KERNEL32!GetProcAddress` at `0x14000d0ca`

## string_xrefs

- `0x14000d0ac`: `ntdll.dll`
- `0x14000d0c0`: `NtUpdateWnfStateData`

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
0x14000d07c  mov     [rsp+arg_0], rbx
0x14000d081  mov     [rsp+arg_8], rsi
0x14000d086  push    rdi
0x14000d087  sub     rsp, 40h
0x14000d08b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000d092  mov     ebx, r8d
0x14000d095  mov     rdi, rdx
0x14000d098  mov     rsi, rcx
0x14000d09b  test    r10, r10
0x14000d09e  jnz     short loc_14000D0E6
0x14000d0a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d0a7  test    rax, rax
0x14000d0aa  jnz     short loc_14000D0C0
0x14000d0ac  lea     rcx, ModuleName; "ntdll.dll"
0x14000d0b3  call    cs:__imp_GetModuleHandleW
0x14000d0b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d0c0  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000d0c7  mov     rcx, rax; hModule
0x14000d0ca  call    cs:__imp_GetProcAddress
0x14000d0d0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000d0d7  mov     r10, rax
0x14000d0da  test    rax, rax
0x14000d0dd  jnz     short loc_14000D0E6
0x14000d0df  mov     eax, 0C0000139h
0x14000d0e4  jmp     short loc_14000D116
0x14000d0e6  mov     eax, [rsp+48h+arg_30]
0x14000d0ed  xor     r9d, r9d
0x14000d0f0  mov     [rsp+48h+var_18], eax
0x14000d0f4  mov     r8d, ebx
0x14000d0f7  mov     eax, [rsp+48h+arg_28]
0x14000d0fb  mov     rdx, rdi
0x14000d0fe  mov     [rsp+48h+var_20], eax
0x14000d102  mov     rcx, rsi
0x14000d105  mov     rax, r10
0x14000d108  mov     [rsp+48h+var_28], 0
0x14000d111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d116  mov     rbx, [rsp+48h+arg_0]
0x14000d11b  mov     rsi, [rsp+48h+arg_8]
0x14000d120  add     rsp, 40h
0x14000d124  pop     rdi
0x14000d125  retn
```
