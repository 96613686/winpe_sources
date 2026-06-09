# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800584ec`
- end: `0x180058535`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `73`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180057df0`

## callees

- `0x1800584ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180058508`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180058508`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058521`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058521`

## string_xrefs

- `0x180058501`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, lpProcName);
}

```

## disassembly

```asm
0x1800584ec  push    rbx
0x1800584ee  sub     rsp, 20h
0x1800584f2  mov     rbx, rcx
0x1800584f5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800584fc  test    rax, rax
0x1800584ff  jnz     short loc_18005851B
0x180058501  lea     rcx, ModuleName; "ntdll.dll"
0x180058508  call    cs:__imp_GetModuleHandleW
0x18005850f  nop     dword ptr [rax+rax+00h]
0x180058514  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18005851b  mov     rdx, rbx; lpProcName
0x18005851e  mov     rcx, rax; hModule
0x180058521  call    cs:__imp_GetProcAddress
0x180058528  nop     dword ptr [rax+rax+00h]
0x18005852d  nop
0x18005852e  add     rsp, 20h
0x180058532  pop     rbx
0x180058533  retn
```
