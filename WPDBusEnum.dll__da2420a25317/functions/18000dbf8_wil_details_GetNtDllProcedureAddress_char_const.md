# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000dbf8`
- end: `0x18000dc33`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ce80`

## callees

- `0x18000dbf8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc14`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc14`

## string_xrefs

- `0x18000dc0d`: `ntdll.dll`

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
0x18000dbf8  push    rbx
0x18000dbfa  sub     rsp, 20h
0x18000dbfe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dc05  mov     rbx, rcx
0x18000dc08  test    rax, rax
0x18000dc0b  jnz     short loc_18000DC21
0x18000dc0d  lea     rcx, ModuleName; "ntdll.dll"
0x18000dc14  call    cs:__imp_GetModuleHandleW
0x18000dc1a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dc21  mov     rdx, rbx
0x18000dc24  mov     rcx, rax
0x18000dc27  add     rsp, 20h
0x18000dc2b  pop     rbx
0x18000dc2c  jmp     cs:__imp_GetProcAddress
```
