# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180006d58`
- end: `0x180006d93`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006040`

## callees

- `0x180006d58`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d74`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d8c`

## string_xrefs

- `0x180006d6d`: `ntdll.dll`

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
0x180006d58  push    rbx
0x180006d5a  sub     rsp, 20h
0x180006d5e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d65  mov     rbx, rcx
0x180006d68  test    rax, rax
0x180006d6b  jnz     short loc_180006D81
0x180006d6d  lea     rcx, aNtdllDll; "ntdll.dll"
0x180006d74  call    cs:__imp_GetModuleHandleW
0x180006d7a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006d81  mov     rdx, rbx
0x180006d84  mov     rcx, rax
0x180006d87  add     rsp, 20h
0x180006d8b  pop     rbx
0x180006d8c  jmp     cs:__imp_GetProcAddress
```
