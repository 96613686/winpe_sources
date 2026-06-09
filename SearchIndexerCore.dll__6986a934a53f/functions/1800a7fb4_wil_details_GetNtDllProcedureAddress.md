# wil_details_GetNtDllProcedureAddress

- ea: `0x1800a7fb4`
- end: `0x1800a7fef`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800a76e0`
- `0x1800a780c`

## callees

- `0x1800a7fb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a7fd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a7fd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7fe8`

## string_xrefs

- `0x1800a7fc9`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const CHAR *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x1800a7fb4  push    rbx
0x1800a7fb6  sub     rsp, 20h
0x1800a7fba  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800a7fc1  mov     rbx, rcx
0x1800a7fc4  test    rax, rax
0x1800a7fc7  jnz     short loc_1800A7FDD
0x1800a7fc9  lea     rcx, ModuleName; "ntdll.dll"
0x1800a7fd0  call    cs:__imp_GetModuleHandleW
0x1800a7fd6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x1800a7fdd  mov     rdx, rbx
0x1800a7fe0  mov     rcx, rax
0x1800a7fe3  add     rsp, 20h
0x1800a7fe7  pop     rbx
0x1800a7fe8  jmp     cs:__imp_GetProcAddress
```
