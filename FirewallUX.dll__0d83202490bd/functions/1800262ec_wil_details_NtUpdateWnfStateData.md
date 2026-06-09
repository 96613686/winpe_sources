# wil_details_NtUpdateWnfStateData

- ea: `0x1800262ec`
- end: `0x180026396`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180025260`
- `0x1800260ac`

## callees

- `0x1800262ec`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026323`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002633a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002633a`

## string_xrefs

- `0x18002631c`: `ntdll.dll`
- `0x180026330`: `NtUpdateWnfStateData`

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
0x1800262ec  mov     [rsp+arg_0], rbx
0x1800262f1  mov     [rsp+arg_8], rsi
0x1800262f6  push    rdi
0x1800262f7  sub     rsp, 40h
0x1800262fb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180026302  mov     ebx, r8d
0x180026305  mov     rdi, rdx
0x180026308  mov     rsi, rcx
0x18002630b  test    r10, r10
0x18002630e  jnz     short loc_180026356
0x180026310  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026317  test    rax, rax
0x18002631a  jnz     short loc_180026330
0x18002631c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180026323  call    cs:__imp_GetModuleHandleW
0x180026329  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026330  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180026337  mov     rcx, rax; hModule
0x18002633a  call    cs:__imp_GetProcAddress
0x180026340  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180026347  mov     r10, rax
0x18002634a  test    rax, rax
0x18002634d  jnz     short loc_180026356
0x18002634f  mov     eax, 0C0000139h
0x180026354  jmp     short loc_180026386
0x180026356  mov     eax, [rsp+48h+arg_30]
0x18002635d  xor     r9d, r9d
0x180026360  mov     [rsp+48h+var_18], eax
0x180026364  mov     r8d, ebx
0x180026367  mov     eax, [rsp+48h+arg_28]
0x18002636b  mov     rdx, rdi
0x18002636e  mov     [rsp+48h+var_20], eax
0x180026372  mov     rcx, rsi
0x180026375  mov     rax, r10
0x180026378  mov     [rsp+48h+var_28], 0
0x180026381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026386  mov     rbx, [rsp+48h+arg_0]
0x18002638b  mov     rsi, [rsp+48h+arg_8]
0x180026390  add     rsp, 40h
0x180026394  pop     rdi
0x180026395  retn
```
