# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800056fc`
- end: `0x180005737`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004c00`

## callees

- `0x1800056fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005730`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005718`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005718`

## string_xrefs

- `0x180005711`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
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
0x1800056fc  push    rbx
0x1800056fe  sub     rsp, 20h
0x180005702  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005709  mov     rbx, rcx
0x18000570c  test    rax, rax
0x18000570f  jnz     short loc_180005725
0x180005711  lea     rcx, ModuleName; "ntdll.dll"
0x180005718  call    cs:__imp_GetModuleHandleW
0x18000571e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005725  mov     rdx, rbx
0x180005728  mov     rcx, rax
0x18000572b  add     rsp, 20h
0x18000572f  pop     rbx
0x180005730  jmp     cs:__imp_GetProcAddress
```
