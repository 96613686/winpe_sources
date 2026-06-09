# wil_details_NtUpdateWnfStateData

- ea: `0x18000aed8`
- end: `0x18000af8f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180007350`
- `0x1800099bc`

## callees

- `0x18000aed8`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000af2c`
- `KERNEL32!GetProcAddress` at `0x18000af2c`
- `KERNEL32!GetModuleHandleW` at `0x18000af0f`
- `KERNEL32!GetModuleHandleW` at `0x18000af0f`

## string_xrefs

- `0x18000af08`: `ntdll.dll`
- `0x18000af22`: `NtUpdateWnfStateData`

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
0x18000aed8  mov     [rsp+arg_0], rbx
0x18000aedd  mov     [rsp+arg_8], rsi
0x18000aee2  push    rdi
0x18000aee3  sub     rsp, 40h
0x18000aee7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000aeee  mov     ebx, r8d
0x18000aef1  mov     rdi, rdx
0x18000aef4  mov     rsi, rcx
0x18000aef7  test    r10, r10
0x18000aefa  jnz     short loc_18000AF4E
0x18000aefc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000af03  test    rax, rax
0x18000af06  jnz     short loc_18000AF22
0x18000af08  lea     rcx, ModuleName; "ntdll.dll"
0x18000af0f  call    cs:__imp_GetModuleHandleW
0x18000af16  nop     dword ptr [rax+rax+00h]
0x18000af1b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000af22  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000af29  mov     rcx, rax; hModule
0x18000af2c  call    cs:__imp_GetProcAddress
0x18000af33  nop     dword ptr [rax+rax+00h]
0x18000af38  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000af3f  mov     r10, rax
0x18000af42  test    rax, rax
0x18000af45  jnz     short loc_18000AF4E
0x18000af47  mov     eax, 0C0000139h
0x18000af4c  jmp     short loc_18000AF7E
0x18000af4e  mov     eax, [rsp+48h+arg_30]
0x18000af55  xor     r9d, r9d
0x18000af58  mov     [rsp+48h+var_18], eax
0x18000af5c  mov     r8d, ebx
0x18000af5f  mov     eax, [rsp+48h+arg_28]
0x18000af63  mov     rdx, rdi
0x18000af66  mov     [rsp+48h+var_20], eax
0x18000af6a  mov     rcx, rsi
0x18000af6d  mov     rax, r10
0x18000af70  mov     [rsp+48h+var_28], 0
0x18000af79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af7e  mov     rbx, [rsp+48h+arg_0]
0x18000af83  mov     rsi, [rsp+48h+arg_8]
0x18000af88  add     rsp, 40h
0x18000af8c  pop     rdi
0x18000af8d  retn
```
