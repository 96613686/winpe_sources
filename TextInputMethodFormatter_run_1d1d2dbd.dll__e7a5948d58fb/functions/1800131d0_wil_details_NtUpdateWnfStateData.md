# wil_details_NtUpdateWnfStateData

- ea: `0x1800131d0`
- end: `0x18001327a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000fadc`
- `0x180012764`

## callees

- `0x1800131d0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001321e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001321e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013207`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013207`

## string_xrefs

- `0x180013200`: `ntdll.dll`
- `0x180013214`: `NtUpdateWnfStateData`

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
0x1800131d0  mov     [rsp+arg_0], rbx
0x1800131d5  mov     [rsp+arg_8], rsi
0x1800131da  push    rdi
0x1800131db  sub     rsp, 40h
0x1800131df  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800131e6  mov     ebx, r8d
0x1800131e9  mov     rdi, rdx
0x1800131ec  mov     rsi, rcx
0x1800131ef  test    r10, r10
0x1800131f2  jnz     short loc_18001323A
0x1800131f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800131fb  test    rax, rax
0x1800131fe  jnz     short loc_180013214
0x180013200  lea     rcx, ModuleName; "ntdll.dll"
0x180013207  call    cs:__imp_GetModuleHandleW
0x18001320d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013214  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001321b  mov     rcx, rax; hModule
0x18001321e  call    cs:__imp_GetProcAddress
0x180013224  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001322b  mov     r10, rax
0x18001322e  test    rax, rax
0x180013231  jnz     short loc_18001323A
0x180013233  mov     eax, 0C0000139h
0x180013238  jmp     short loc_18001326A
0x18001323a  mov     eax, [rsp+48h+arg_30]
0x180013241  xor     r9d, r9d
0x180013244  mov     [rsp+48h+var_18], eax
0x180013248  mov     r8d, ebx
0x18001324b  mov     eax, [rsp+48h+arg_28]
0x18001324f  mov     rdx, rdi
0x180013252  mov     [rsp+48h+var_20], eax
0x180013256  mov     rcx, rsi
0x180013259  mov     rax, r10
0x18001325c  mov     [rsp+48h+var_28], 0
0x180013265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001326a  mov     rbx, [rsp+48h+arg_0]
0x18001326f  mov     rsi, [rsp+48h+arg_8]
0x180013274  add     rsp, 40h
0x180013278  pop     rdi
0x180013279  retn
```
