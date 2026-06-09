# wil_details_GetNtDllProcedureAddress

- ea: `0x180008020`
- end: `0x18000805b`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800076e0`
- `0x1800077d8`

## callees

- `0x180008020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000803c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000803c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008054`

## string_xrefs

- `0x180008035`: `ntdll.dll`

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
0x180008020  push    rbx
0x180008022  sub     rsp, 20h
0x180008026  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000802d  mov     rbx, rcx
0x180008030  test    rax, rax
0x180008033  jnz     short loc_180008049
0x180008035  lea     rcx, ModuleName; "ntdll.dll"
0x18000803c  call    cs:__imp_GetModuleHandleW
0x180008042  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180008049  mov     rdx, rbx
0x18000804c  mov     rcx, rax
0x18000804f  add     rsp, 20h
0x180008053  pop     rbx
0x180008054  jmp     cs:__imp_GetProcAddress
```
