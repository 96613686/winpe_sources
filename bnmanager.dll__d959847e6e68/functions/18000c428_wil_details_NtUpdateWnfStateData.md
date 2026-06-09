# wil_details_NtUpdateWnfStateData

- ea: `0x18000c428`
- end: `0x18000c4d2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009bfc`
- `0x18000c158`

## callees

- `0x18000c428`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c45f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c45f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c476`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c476`

## string_xrefs

- `0x18000c458`: `ntdll.dll`
- `0x18000c46c`: `NtUpdateWnfStateData`

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
0x18000c428  mov     [rsp+arg_0], rbx
0x18000c42d  mov     [rsp+arg_8], rsi
0x18000c432  push    rdi
0x18000c433  sub     rsp, 40h
0x18000c437  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000c43e  mov     ebx, r8d
0x18000c441  mov     rdi, rdx
0x18000c444  mov     rsi, rcx
0x18000c447  test    r10, r10
0x18000c44a  jnz     short loc_18000C492
0x18000c44c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c453  test    rax, rax
0x18000c456  jnz     short loc_18000C46C
0x18000c458  lea     rcx, ModuleName; "ntdll.dll"
0x18000c45f  call    cs:__imp_GetModuleHandleW
0x18000c465  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c46c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000c473  mov     rcx, rax; hModule
0x18000c476  call    cs:__imp_GetProcAddress
0x18000c47c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000c483  mov     r10, rax
0x18000c486  test    rax, rax
0x18000c489  jnz     short loc_18000C492
0x18000c48b  mov     eax, 0C0000139h
0x18000c490  jmp     short loc_18000C4C2
0x18000c492  mov     eax, [rsp+48h+arg_30]
0x18000c499  xor     r9d, r9d
0x18000c49c  mov     [rsp+48h+var_18], eax
0x18000c4a0  mov     r8d, ebx
0x18000c4a3  mov     eax, [rsp+48h+arg_28]
0x18000c4a7  mov     rdx, rdi
0x18000c4aa  mov     [rsp+48h+var_20], eax
0x18000c4ae  mov     rcx, rsi
0x18000c4b1  mov     rax, r10
0x18000c4b4  mov     [rsp+48h+var_28], 0
0x18000c4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4c2  mov     rbx, [rsp+48h+arg_0]
0x18000c4c7  mov     rsi, [rsp+48h+arg_8]
0x18000c4cc  add     rsp, 40h
0x18000c4d0  pop     rdi
0x18000c4d1  retn
```
