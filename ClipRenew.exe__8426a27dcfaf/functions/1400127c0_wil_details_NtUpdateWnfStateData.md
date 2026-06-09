# wil_details_NtUpdateWnfStateData

- ea: `0x1400127c0`
- end: `0x14001286a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140010a9c`
- `0x1400120a8`

## callees

- `0x1400127c0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001280e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001280e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400127f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400127f7`

## string_xrefs

- `0x1400127f0`: `ntdll.dll`
- `0x140012804`: `NtUpdateWnfStateData`

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
0x1400127c0  mov     [rsp+arg_0], rbx
0x1400127c5  mov     [rsp+arg_8], rsi
0x1400127ca  push    rdi
0x1400127cb  sub     rsp, 40h
0x1400127cf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400127d6  mov     ebx, r8d
0x1400127d9  mov     rdi, rdx
0x1400127dc  mov     rsi, rcx
0x1400127df  test    r10, r10
0x1400127e2  jnz     short loc_14001282A
0x1400127e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400127eb  test    rax, rax
0x1400127ee  jnz     short loc_140012804
0x1400127f0  lea     rcx, ModuleName; "ntdll.dll"
0x1400127f7  call    cs:__imp_GetModuleHandleW
0x1400127fd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012804  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14001280b  mov     rcx, rax; hModule
0x14001280e  call    cs:__imp_GetProcAddress
0x140012814  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14001281b  mov     r10, rax
0x14001281e  test    rax, rax
0x140012821  jnz     short loc_14001282A
0x140012823  mov     eax, 0C0000139h
0x140012828  jmp     short loc_14001285A
0x14001282a  mov     eax, [rsp+48h+arg_30]
0x140012831  xor     r9d, r9d
0x140012834  mov     [rsp+48h+var_18], eax
0x140012838  mov     r8d, ebx
0x14001283b  mov     eax, [rsp+48h+arg_28]
0x14001283f  mov     rdx, rdi
0x140012842  mov     [rsp+48h+var_20], eax
0x140012846  mov     rcx, rsi
0x140012849  mov     rax, r10
0x14001284c  mov     [rsp+48h+var_28], 0
0x140012855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001285a  mov     rbx, [rsp+48h+arg_0]
0x14001285f  mov     rsi, [rsp+48h+arg_8]
0x140012864  add     rsp, 40h
0x140012868  pop     rdi
0x140012869  retn
```
