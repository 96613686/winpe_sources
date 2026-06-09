# wil_details_NtUpdateWnfStateData

- ea: `0x14006eed8`
- end: `0x14006ef82`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14006b830`
- `0x14006d670`

## callees

- `0x14006eed8`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14006ef26`
- `KERNEL32!GetProcAddress` at `0x14006ef26`
- `KERNEL32!GetModuleHandleW` at `0x14006ef0f`
- `KERNEL32!GetModuleHandleW` at `0x14006ef0f`

## string_xrefs

- `0x14006ef08`: `ntdll.dll`
- `0x14006ef1c`: `NtUpdateWnfStateData`

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
0x14006eed8  mov     [rsp+arg_0], rbx
0x14006eedd  mov     [rsp+arg_8], rsi
0x14006eee2  push    rdi
0x14006eee3  sub     rsp, 40h
0x14006eee7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14006eeee  mov     ebx, r8d
0x14006eef1  mov     rdi, rdx
0x14006eef4  mov     rsi, rcx
0x14006eef7  test    r10, r10
0x14006eefa  jnz     short loc_14006EF42
0x14006eefc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006ef03  test    rax, rax
0x14006ef06  jnz     short loc_14006EF1C
0x14006ef08  lea     rcx, ModuleName; "ntdll.dll"
0x14006ef0f  call    cs:__imp_GetModuleHandleW
0x14006ef15  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006ef1c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14006ef23  mov     rcx, rax; hModule
0x14006ef26  call    cs:__imp_GetProcAddress
0x14006ef2c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14006ef33  mov     r10, rax
0x14006ef36  test    rax, rax
0x14006ef39  jnz     short loc_14006EF42
0x14006ef3b  mov     eax, 0C0000139h
0x14006ef40  jmp     short loc_14006EF72
0x14006ef42  mov     eax, [rsp+48h+arg_30]
0x14006ef49  xor     r9d, r9d
0x14006ef4c  mov     [rsp+48h+var_18], eax
0x14006ef50  mov     r8d, ebx
0x14006ef53  mov     eax, [rsp+48h+arg_28]
0x14006ef57  mov     rdx, rdi
0x14006ef5a  mov     [rsp+48h+var_20], eax
0x14006ef5e  mov     rcx, rsi
0x14006ef61  mov     rax, r10
0x14006ef64  mov     [rsp+48h+var_28], 0
0x14006ef6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ef72  mov     rbx, [rsp+48h+arg_0]
0x14006ef77  mov     rsi, [rsp+48h+arg_8]
0x14006ef7c  add     rsp, 40h
0x14006ef80  pop     rdi
0x14006ef81  retn
```
