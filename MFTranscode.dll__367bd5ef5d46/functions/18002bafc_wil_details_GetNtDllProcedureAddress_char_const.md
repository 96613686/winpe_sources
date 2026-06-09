# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002bafc`
- end: `0x18002bb37`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800212c0`

## callees

- `0x18002bafc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bb18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bb18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb30`

## string_xrefs

- `0x18002bb11`: `ntdll.dll`

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
0x18002bafc  push    rbx
0x18002bafe  sub     rsp, 20h
0x18002bb02  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002bb09  mov     rbx, rcx
0x18002bb0c  test    rax, rax
0x18002bb0f  jnz     short loc_18002BB25
0x18002bb11  lea     rcx, ModuleName; "ntdll.dll"
0x18002bb18  call    cs:__imp_GetModuleHandleW
0x18002bb1e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002bb25  mov     rdx, rbx
0x18002bb28  mov     rcx, rax
0x18002bb2b  add     rsp, 20h
0x18002bb2f  pop     rbx
0x18002bb30  jmp     cs:__imp_GetProcAddress
```
