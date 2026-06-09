# wil_details_NtUpdateWnfStateData

- ea: `0x1800226a0`
- end: `0x18002274a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800142d0`
- `0x180021f90`

## callees

- `0x1800226a0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800226d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800226d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800226ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800226ee`

## string_xrefs

- `0x1800226d0`: `ntdll.dll`
- `0x1800226e4`: `NtUpdateWnfStateData`

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
0x1800226a0  mov     [rsp+arg_0], rbx
0x1800226a5  mov     [rsp+arg_8], rsi
0x1800226aa  push    rdi
0x1800226ab  sub     rsp, 40h
0x1800226af  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800226b6  mov     ebx, r8d
0x1800226b9  mov     rdi, rdx
0x1800226bc  mov     rsi, rcx
0x1800226bf  test    r10, r10
0x1800226c2  jnz     short loc_18002270A
0x1800226c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800226cb  test    rax, rax
0x1800226ce  jnz     short loc_1800226E4
0x1800226d0  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x1800226d7  call    cs:__imp_GetModuleHandleW
0x1800226dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800226e4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800226eb  mov     rcx, rax; hModule
0x1800226ee  call    cs:__imp_GetProcAddress
0x1800226f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800226fb  mov     r10, rax
0x1800226fe  test    rax, rax
0x180022701  jnz     short loc_18002270A
0x180022703  mov     eax, 0C0000139h
0x180022708  jmp     short loc_18002273A
0x18002270a  mov     eax, [rsp+48h+arg_30]
0x180022711  xor     r9d, r9d
0x180022714  mov     [rsp+48h+var_18], eax
0x180022718  mov     r8d, ebx
0x18002271b  mov     eax, [rsp+48h+arg_28]
0x18002271f  mov     rdx, rdi
0x180022722  mov     [rsp+48h+var_20], eax
0x180022726  mov     rcx, rsi
0x180022729  mov     rax, r10
0x18002272c  mov     [rsp+48h+var_28], 0
0x180022735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002273a  mov     rbx, [rsp+48h+arg_0]
0x18002273f  mov     rsi, [rsp+48h+arg_8]
0x180022744  add     rsp, 40h
0x180022748  pop     rdi
0x180022749  retn
```
