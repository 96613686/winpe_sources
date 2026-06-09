# wil_details_GetNtDllProcedureAddress

- ea: `0x180022664`
- end: `0x18002269f`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180021d48`
- `0x18002233c`

## callees

- `0x180022664`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022698`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022680`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022680`

## string_xrefs

- `0x180022679`: `ntdll.dll`

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
0x180022664  push    rbx
0x180022666  sub     rsp, 20h
0x18002266a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180022671  mov     rbx, rcx
0x180022674  test    rax, rax
0x180022677  jnz     short loc_18002268D
0x180022679  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180022680  call    cs:__imp_GetModuleHandleW
0x180022686  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002268d  mov     rdx, rbx
0x180022690  mov     rcx, rax
0x180022693  add     rsp, 20h
0x180022697  pop     rbx
0x180022698  jmp     cs:__imp_GetProcAddress
```
