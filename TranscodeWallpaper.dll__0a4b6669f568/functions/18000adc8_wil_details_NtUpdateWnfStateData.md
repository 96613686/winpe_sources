# wil_details_NtUpdateWnfStateData

- ea: `0x18000adc8`
- end: `0x18000ae72`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009790`
- `0x18000ab88`

## callees

- `0x18000adc8`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae16`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000adff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000adff`

## string_xrefs

- `0x18000adf8`: `ntdll.dll`
- `0x18000ae0c`: `NtUpdateWnfStateData`

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
0x18000adc8  mov     [rsp+arg_0], rbx
0x18000adcd  mov     [rsp+arg_8], rsi
0x18000add2  push    rdi
0x18000add3  sub     rsp, 40h
0x18000add7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000adde  mov     ebx, r8d
0x18000ade1  mov     rdi, rdx
0x18000ade4  mov     rsi, rcx
0x18000ade7  test    r10, r10
0x18000adea  jnz     short loc_18000AE32
0x18000adec  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000adf3  test    rax, rax
0x18000adf6  jnz     short loc_18000AE0C
0x18000adf8  lea     rcx, ModuleName; "ntdll.dll"
0x18000adff  call    cs:__imp_GetModuleHandleW
0x18000ae05  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ae0c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ae13  mov     rcx, rax; hModule
0x18000ae16  call    cs:__imp_GetProcAddress
0x18000ae1c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ae23  mov     r10, rax
0x18000ae26  test    rax, rax
0x18000ae29  jnz     short loc_18000AE32
0x18000ae2b  mov     eax, 0C0000139h
0x18000ae30  jmp     short loc_18000AE62
0x18000ae32  mov     eax, [rsp+48h+arg_30]
0x18000ae39  xor     r9d, r9d
0x18000ae3c  mov     [rsp+48h+var_18], eax
0x18000ae40  mov     r8d, ebx
0x18000ae43  mov     eax, [rsp+48h+arg_28]
0x18000ae47  mov     rdx, rdi
0x18000ae4a  mov     [rsp+48h+var_20], eax
0x18000ae4e  mov     rcx, rsi
0x18000ae51  mov     rax, r10
0x18000ae54  mov     [rsp+48h+var_28], 0
0x18000ae5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae62  mov     rbx, [rsp+48h+arg_0]
0x18000ae67  mov     rsi, [rsp+48h+arg_8]
0x18000ae6c  add     rsp, 40h
0x18000ae70  pop     rdi
0x18000ae71  retn
```
