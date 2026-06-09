# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800a0e5c`
- end: `0x1800a0ea2`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `70`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800a01d0`

## callees

- `0x1800a0e5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a0e96`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a0e78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a0e78`

## string_xrefs

- `0x1800a0e71`: `ntdll.dll`

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
0x1800a0e5c  push    rbx
0x1800a0e5e  sub     rsp, 20h
0x1800a0e62  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800a0e69  mov     rbx, rcx
0x1800a0e6c  test    rax, rax
0x1800a0e6f  jnz     short loc_1800A0E8B
0x1800a0e71  lea     rcx, ModuleName; "ntdll.dll"
0x1800a0e78  call    cs:__imp_GetModuleHandleW
0x1800a0e7f  nop     dword ptr [rax+rax+00h]
0x1800a0e84  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800a0e8b  mov     rdx, rbx
0x1800a0e8e  mov     rcx, rax
0x1800a0e91  add     rsp, 20h
0x1800a0e95  pop     rbx
0x1800a0e96  jmp     cs:__imp_GetProcAddress
```
