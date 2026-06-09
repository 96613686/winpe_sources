# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180034b2c`
- end: `0x180034b67`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180034af0`
- `0x180047280`

## callees

- `0x180034b2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034b60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034b48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034b48`

## string_xrefs

- `0x180034b41`: `ntdll.dll`

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
0x180034b2c  push    rbx
0x180034b2e  sub     rsp, 20h
0x180034b32  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180034b39  mov     rbx, rcx
0x180034b3c  test    rax, rax
0x180034b3f  jnz     short loc_180034B55
0x180034b41  lea     rcx, ModuleName; "ntdll.dll"
0x180034b48  call    cs:__imp_GetModuleHandleW
0x180034b4e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180034b55  mov     rdx, rbx
0x180034b58  mov     rcx, rax
0x180034b5b  add     rsp, 20h
0x180034b5f  pop     rbx
0x180034b60  jmp     cs:__imp_GetProcAddress
```
