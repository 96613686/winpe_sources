# wil_details_GetNtDllProcedureAddress

- ea: `0x18000b464`
- end: `0x18000b49f`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: `FARPROC __fastcall(const CHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ab10`
- `0x18000b120`

## callees

- `0x18000b464`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b480`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b480`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b498`

## string_xrefs

- `0x18000b479`: `ntdll.dll`

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
0x18000b464  push    rbx
0x18000b466  sub     rsp, 20h
0x18000b46a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000b471  mov     rbx, rcx
0x18000b474  test    rax, rax
0x18000b477  jnz     short loc_18000B48D
0x18000b479  lea     rcx, ModuleName; "ntdll.dll"
0x18000b480  call    cs:__imp_GetModuleHandleW
0x18000b486  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000b48d  mov     rdx, rbx
0x18000b490  mov     rcx, rax
0x18000b493  add     rsp, 20h
0x18000b497  pop     rbx
0x18000b498  jmp     cs:__imp_GetProcAddress
```
