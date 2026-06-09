# wil_details_NtUpdateWnfStateData

- ea: `0x18000a048`
- end: `0x18000a0f2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008648`
- `0x180009e08`

## callees

- `0x18000a048`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a096`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a07f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a07f`

## string_xrefs

- `0x18000a078`: `ntdll.dll`
- `0x18000a08c`: `NtUpdateWnfStateData`

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
0x18000a048  mov     [rsp+arg_0], rbx
0x18000a04d  mov     [rsp+arg_8], rsi
0x18000a052  push    rdi
0x18000a053  sub     rsp, 40h
0x18000a057  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a05e  mov     ebx, r8d
0x18000a061  mov     rdi, rdx
0x18000a064  mov     rsi, rcx
0x18000a067  test    r10, r10
0x18000a06a  jnz     short loc_18000A0B2
0x18000a06c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a073  test    rax, rax
0x18000a076  jnz     short loc_18000A08C
0x18000a078  lea     rcx, ModuleName; "ntdll.dll"
0x18000a07f  call    cs:__imp_GetModuleHandleW
0x18000a085  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a08c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a093  mov     rcx, rax; hModule
0x18000a096  call    cs:__imp_GetProcAddress
0x18000a09c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a0a3  mov     r10, rax
0x18000a0a6  test    rax, rax
0x18000a0a9  jnz     short loc_18000A0B2
0x18000a0ab  mov     eax, 0C0000139h
0x18000a0b0  jmp     short loc_18000A0E2
0x18000a0b2  mov     eax, [rsp+48h+arg_30]
0x18000a0b9  xor     r9d, r9d
0x18000a0bc  mov     [rsp+48h+var_18], eax
0x18000a0c0  mov     r8d, ebx
0x18000a0c3  mov     eax, [rsp+48h+arg_28]
0x18000a0c7  mov     rdx, rdi
0x18000a0ca  mov     [rsp+48h+var_20], eax
0x18000a0ce  mov     rcx, rsi
0x18000a0d1  mov     rax, r10
0x18000a0d4  mov     [rsp+48h+var_28], 0
0x18000a0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e2  mov     rbx, [rsp+48h+arg_0]
0x18000a0e7  mov     rsi, [rsp+48h+arg_8]
0x18000a0ec  add     rsp, 40h
0x18000a0f0  pop     rdi
0x18000a0f1  retn
```
