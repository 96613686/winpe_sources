# wil_details_NtUpdateWnfStateData

- ea: `0x180003118`
- end: `0x1800031c2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180004f04`
- `0x1800070c0`

## callees

- `0x180003118`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000314f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000314f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003166`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003166`

## string_xrefs

- `0x180003148`: `ntdll.dll`
- `0x18000315c`: `NtUpdateWnfStateData`

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
0x180003118  mov     [rsp+arg_0], rbx
0x18000311d  mov     [rsp+arg_8], rsi
0x180003122  push    rdi
0x180003123  sub     rsp, 40h
0x180003127  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000312e  mov     ebx, r8d
0x180003131  mov     rdi, rdx
0x180003134  mov     rsi, rcx
0x180003137  test    r10, r10
0x18000313a  jnz     short loc_180003182
0x18000313c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003143  test    rax, rax
0x180003146  jnz     short loc_18000315C
0x180003148  lea     rcx, ModuleName; "ntdll.dll"
0x18000314f  call    cs:__imp_GetModuleHandleW
0x180003155  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000315c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180003163  mov     rcx, rax; hModule
0x180003166  call    cs:__imp_GetProcAddress
0x18000316c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180003173  mov     r10, rax
0x180003176  test    rax, rax
0x180003179  jnz     short loc_180003182
0x18000317b  mov     eax, 0C0000139h
0x180003180  jmp     short loc_1800031B2
0x180003182  mov     eax, [rsp+48h+arg_30]
0x180003189  xor     r9d, r9d
0x18000318c  mov     [rsp+48h+var_18], eax
0x180003190  mov     r8d, ebx
0x180003193  mov     eax, [rsp+48h+arg_28]
0x180003197  mov     rdx, rdi
0x18000319a  mov     [rsp+48h+var_20], eax
0x18000319e  mov     rcx, rsi
0x1800031a1  mov     rax, r10
0x1800031a4  mov     [rsp+48h+var_28], 0
0x1800031ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b2  mov     rbx, [rsp+48h+arg_0]
0x1800031b7  mov     rsi, [rsp+48h+arg_8]
0x1800031bc  add     rsp, 40h
0x1800031c0  pop     rdi
0x1800031c1  retn
```
