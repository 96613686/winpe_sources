# wil_details_NtUpdateWnfStateData

- ea: `0x180010160`
- end: `0x18001020a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000afdc`
- `0x18000f698`

## callees

- `0x180010160`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010197`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010197`

## string_xrefs

- `0x180010190`: `ntdll.dll`
- `0x1800101a4`: `NtUpdateWnfStateData`

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
0x180010160  mov     [rsp+arg_0], rbx
0x180010165  mov     [rsp+arg_8], rsi
0x18001016a  push    rdi
0x18001016b  sub     rsp, 40h
0x18001016f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180010176  mov     ebx, r8d
0x180010179  mov     rdi, rdx
0x18001017c  mov     rsi, rcx
0x18001017f  test    r10, r10
0x180010182  jnz     short loc_1800101CA
0x180010184  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001018b  test    rax, rax
0x18001018e  jnz     short loc_1800101A4
0x180010190  lea     rcx, ModuleName; "ntdll.dll"
0x180010197  call    cs:__imp_GetModuleHandleW
0x18001019d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800101a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800101ab  mov     rcx, rax; hModule
0x1800101ae  call    cs:__imp_GetProcAddress
0x1800101b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800101bb  mov     r10, rax
0x1800101be  test    rax, rax
0x1800101c1  jnz     short loc_1800101CA
0x1800101c3  mov     eax, 0C0000139h
0x1800101c8  jmp     short loc_1800101FA
0x1800101ca  mov     eax, [rsp+48h+arg_30]
0x1800101d1  xor     r9d, r9d
0x1800101d4  mov     [rsp+48h+var_18], eax
0x1800101d8  mov     r8d, ebx
0x1800101db  mov     eax, [rsp+48h+arg_28]
0x1800101df  mov     rdx, rdi
0x1800101e2  mov     [rsp+48h+var_20], eax
0x1800101e6  mov     rcx, rsi
0x1800101e9  mov     rax, r10
0x1800101ec  mov     [rsp+48h+var_28], 0
0x1800101f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101fa  mov     rbx, [rsp+48h+arg_0]
0x1800101ff  mov     rsi, [rsp+48h+arg_8]
0x180010204  add     rsp, 40h
0x180010208  pop     rdi
0x180010209  retn
```
