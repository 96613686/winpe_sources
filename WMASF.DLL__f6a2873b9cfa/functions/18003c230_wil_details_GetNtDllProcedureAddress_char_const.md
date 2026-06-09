# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18003c230`
- end: `0x18003c26b`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003a960`

## callees

- `0x18003c230`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003c264`
- `KERNEL32!GetModuleHandleW` at `0x18003c24c`
- `KERNEL32!GetModuleHandleW` at `0x18003c24c`

## string_xrefs

- `0x18003c245`: `ntdll.dll`

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
0x18003c230  push    rbx
0x18003c232  sub     rsp, 20h
0x18003c236  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003c23d  mov     rbx, rcx
0x18003c240  test    rax, rax
0x18003c243  jnz     short loc_18003C259
0x18003c245  lea     rcx, ModuleName; "ntdll.dll"
0x18003c24c  call    cs:__imp_GetModuleHandleW
0x18003c252  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003c259  mov     rdx, rbx
0x18003c25c  mov     rcx, rax
0x18003c25f  add     rsp, 20h
0x18003c263  pop     rbx
0x18003c264  jmp     cs:__imp_GetProcAddress
```
