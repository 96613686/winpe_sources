# wil_details_NtUpdateWnfStateData

- ea: `0x180008f98`
- end: `0x180009042`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000683c`
- `0x180008c88`

## callees

- `0x180008f98`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008fe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008fcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008fcf`

## string_xrefs

- `0x180008fc8`: `ntdll.dll`
- `0x180008fdc`: `NtUpdateWnfStateData`

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
0x180008f98  mov     [rsp+arg_0], rbx
0x180008f9d  mov     [rsp+arg_8], rsi
0x180008fa2  push    rdi
0x180008fa3  sub     rsp, 40h
0x180008fa7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180008fae  mov     ebx, r8d
0x180008fb1  mov     rdi, rdx
0x180008fb4  mov     rsi, rcx
0x180008fb7  test    r10, r10
0x180008fba  jnz     short loc_180009002
0x180008fbc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008fc3  test    rax, rax
0x180008fc6  jnz     short loc_180008FDC
0x180008fc8  lea     rcx, ModuleName; "ntdll.dll"
0x180008fcf  call    cs:__imp_GetModuleHandleW
0x180008fd5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008fdc  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008fe3  mov     rcx, rax; hModule
0x180008fe6  call    cs:__imp_GetProcAddress
0x180008fec  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180008ff3  mov     r10, rax
0x180008ff6  test    rax, rax
0x180008ff9  jnz     short loc_180009002
0x180008ffb  mov     eax, 0C0000139h
0x180009000  jmp     short loc_180009032
0x180009002  mov     eax, [rsp+48h+arg_30]
0x180009009  xor     r9d, r9d
0x18000900c  mov     [rsp+48h+var_18], eax
0x180009010  mov     r8d, ebx
0x180009013  mov     eax, [rsp+48h+arg_28]
0x180009017  mov     rdx, rdi
0x18000901a  mov     [rsp+48h+var_20], eax
0x18000901e  mov     rcx, rsi
0x180009021  mov     rax, r10
0x180009024  mov     [rsp+48h+var_28], 0
0x18000902d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009032  mov     rbx, [rsp+48h+arg_0]
0x180009037  mov     rsi, [rsp+48h+arg_8]
0x18000903c  add     rsp, 40h
0x180009040  pop     rdi
0x180009041  retn
```
