# wil_details_NtUpdateWnfStateData

- ea: `0x180012d00`
- end: `0x180012daa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180011c80`
- `0x180012ac0`

## callees

- `0x180012d00`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180012d4e`
- `KERNEL32!GetProcAddress` at `0x180012d4e`
- `KERNEL32!GetModuleHandleW` at `0x180012d37`
- `KERNEL32!GetModuleHandleW` at `0x180012d37`

## string_xrefs

- `0x180012d30`: `ntdll.dll`
- `0x180012d44`: `NtUpdateWnfStateData`

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
0x180012d00  mov     [rsp+arg_0], rbx
0x180012d05  mov     [rsp+arg_8], rsi
0x180012d0a  push    rdi
0x180012d0b  sub     rsp, 40h
0x180012d0f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012d16  mov     ebx, r8d
0x180012d19  mov     rdi, rdx
0x180012d1c  mov     rsi, rcx
0x180012d1f  test    r10, r10
0x180012d22  jnz     short loc_180012D6A
0x180012d24  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012d2b  test    rax, rax
0x180012d2e  jnz     short loc_180012D44
0x180012d30  lea     rcx, ModuleName; "ntdll.dll"
0x180012d37  call    cs:__imp_GetModuleHandleW
0x180012d3d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012d44  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180012d4b  mov     rcx, rax; hModule
0x180012d4e  call    cs:__imp_GetProcAddress
0x180012d54  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180012d5b  mov     r10, rax
0x180012d5e  test    rax, rax
0x180012d61  jnz     short loc_180012D6A
0x180012d63  mov     eax, 0C0000139h
0x180012d68  jmp     short loc_180012D9A
0x180012d6a  mov     eax, [rsp+48h+arg_30]
0x180012d71  xor     r9d, r9d
0x180012d74  mov     [rsp+48h+var_18], eax
0x180012d78  mov     r8d, ebx
0x180012d7b  mov     eax, [rsp+48h+arg_28]
0x180012d7f  mov     rdx, rdi
0x180012d82  mov     [rsp+48h+var_20], eax
0x180012d86  mov     rcx, rsi
0x180012d89  mov     rax, r10
0x180012d8c  mov     [rsp+48h+var_28], 0
0x180012d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d9a  mov     rbx, [rsp+48h+arg_0]
0x180012d9f  mov     rsi, [rsp+48h+arg_8]
0x180012da4  add     rsp, 40h
0x180012da8  pop     rdi
0x180012da9  retn
```
